---
uid: Handling_Errors-Delphi
description: Handling_Errors-Delphi
---


# Handling non-fatal errors (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\10\.API\\X0\.Handling Errors** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;10.&#8203;API/&#8203;X0.&#8203;Handling Errors](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/10\.API/X0\.Handling%20Errors)


## Overview


On this demo we are going to see how to deal with errors that are not
fatal and will normally be ignored, but that can degrade the generated
files.

You can hook your own listener to the [TFlexCelTrace](~/api/FlexCel.Core/TFlexCelTrace/index.md) static class to gain
control on what should be done when a non-fatal error happens.

## Concepts

- How to hook a listener to the static [TFlexCelTrace](~/api/FlexCel.Core/TFlexCelTrace/index.md) class. In a normal
  application you would just hook the listener at the beginning of
  the application. On this case, since our demo can be used
  standalone or from the MainDemo browser, we need to make sure we
  unhook the event when the form is disposed.

- How to stop the file generation when a non-fatal error happens.

- How we should take care of threading issues, since [TFlexCelTrace](~/api/FlexCel.Core/TFlexCelTrace/index.md) is a
  static class that could be called from more than one place.

- How to ignore different types of errors.

## Files

### UHandlingErrors.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UHandlingErrors;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, ImgList, ActnList, StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Tabs, Grids,ExtCtrls, ComCtrls, ToolWin, Generics.Collections,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFHandlingErrors = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton1: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton5: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton4: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton6: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Actions: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionGo: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionInfo: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionClose: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    errorBox: TMemo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel1: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbStopOnErrors: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbIgnoreFontErrors: TCheckBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionInfoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionGoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormDestroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ErrorList: TList&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">>;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ErrorListLock: TObject;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FlexCelTrace_OnError</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TFlexCelErrorInfo);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> DoThings</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  EMyAbortException = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Exception);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FHandlingErrors: TFHandlingErrors;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Math, IOUtils, UFlexCelHDPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.ActionInfoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This example shows how to handle non fatal errors using the FlexCelTrace class.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ErrorListLock := TObject.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ErrorList := TList&#x3C;</span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">>.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterForHDPI(Self, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.FormDestroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ErrorList.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ErrorListLock.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.ActionGoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> TFlexCelTrace.OnError := FlexCelTrace_OnError;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> ErrorList.Clear;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4"> errorBox.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   DoThings;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> except</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   on</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ex: EMyAbortException </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">     ShowMessage(ex.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ErrorList.Count = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    errorBox.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">'No errors!'</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    errorBox.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">'There were '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + IntToStr(ErrorList.Count) + </span><span style="color:#A31515;--shiki-dark:#CE9178">' error messages.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s </span><span style="color:#0000FF;--shiki-dark:#569CD6">in</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ErrorList </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      errorBox.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(s);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.DoThings</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  r: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  pdf: TFlexCelPdfExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 1999</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.InsertHPageBreak(r);  </span><span style="color:#008000;--shiki-dark:#6A9955">//This won't throw an exception here, since FlexCel allows to have more than 1025 page breaks, but at the moment of saving. (since an xls file can't have more than that)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'We have a page break on each row, so this will print/export as one row per page'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'??? ? ? ? ???? ????'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Since we leave the font at arial, this won't show when exporting to pdf.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt := xls.GetDefaultFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Arial Unicode MS'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'??? ? ? ? ???? ????'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.AddFormat(fmt));  </span><span style="color:#008000;--shiki-dark:#6A9955">//this will display fine in the pdf.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'ThisFontDoesntExists'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This font doesn''t exists'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.AddFormat(fmt));</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Tahoma doesn't have italic variant. See http://help.lockergnome.com/office/Tahoma-italic-ftopict705661.html</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //You shouldn't normally use Tahoma italics in a document. If we embedded the fonts in this pdf, the fake italics wouldn't work.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Tahoma'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt.Font.Style := [TFlxFontStyles.Italic];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">5</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is fake italics'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.AddFormat(fmt));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    pdf := TFlexCelPdfExport.Create(xls, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Export</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TPath.ChangeExtension(SaveDialog.FileName, </span><span style="color:#A31515;--shiki-dark:#CE9178">'.pdf'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      pdf.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(SaveDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFHandlingErrors.FlexCelTrace_OnError</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TFlexCelErrorInfo);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbIgnoreFontErrors.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e.Error </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">       //Ignore this errors:</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TFlexCelError.PdfFontNotFound, TFlexCelError.PdfGlyphNotInFont, TFlexCelError.PdfFauxBoldOrItalics:</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //If we selected "Stop On Errors" we will abort file generation by throwing an exception that will be</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //catched in the main block.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cbStopOnErrors.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> EMyAbortException.Create(e.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //In this case this is a single thread app so locking is not really necessary,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //but it is a good practice to always lock access to global objects in this error handler.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //This event handler might me called from more than one thread, and you don't want to mess</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //the object collecting the messages (in this case ErrorList).</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.TMonitor.Enter(ErrorListLock);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ErrorList.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(e.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    System.TMonitor.</span><span style="color:#AF00DB;--shiki-dark:#C586C0">Exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ErrorListLock);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



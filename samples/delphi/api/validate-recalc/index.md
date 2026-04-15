---
uid: Validate_Recalc-Delphi
description: Validate_Recalc-Delphi
---


# Validating FlexCel recalculation (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\10\.API\\75\.Validate Recalc** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;10.&#8203;API/&#8203;75.&#8203;Validate Recalc](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/10\.API/75\.Validate%20Recalc)


## Overview


By default, FlexCel recalculates the files it generates before saving.
This is not completely necessary for normal xls/x files, because Excel
will recalculate the file again when opening. But when natively printing
or exporting to PDF, you need the values from the recalculation, because
no Excel is involved in the process.

While most files will recalculate fine, if you have complex formulas and
need to verify they will recalculate ok, this is the application to use.

## Concepts

- **Button \"Validate Recalc\":**
  This will verify that flexcel can understand all the formulas on your
  sheet.

- **Button \"Compare with Excel\":**
  This will open a file you saved with Excel, force a recalculation in
  FlexCel and then compare all formula results with the original ones.
  You can use this to verify the results are actually what you expect
  them to be.

## Files

### UValidateRecalc.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UValidateRecalc;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, ImgList, ActnList, StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Tabs, Grids,ExtCtrls, ComCtrls, ToolWin,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFValidateRecalc = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton1: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton2: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton3: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton5: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton4: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton6: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Actions: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionValidateRecalc: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionCompareWithExcel: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionInfo: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionClose: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenDialog: TOpenDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    report: TMemo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LinkedFileDialog: TOpenDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionValidateRecalcExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionInfoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCompareWithExcelExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Work_LoadLinkedFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TLoadLinkedFileEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CompareXls</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls1, xls2: TXlsFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetErrorType</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f: TUnsupportedFormulaErrorType): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FValidateRecalc: TFValidateRecalc;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Math, IOUtils, UFlexCelHDPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.ActionInfoExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This example will validate the calculations performed by the FlexCel engine.'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  #</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'It can do it in 2 different ways:'</span><span style="color:#000000;--shiki-dark:#D4D4D4">+</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  #</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'  1) The button "Validate Recalc" will analyze a file, and report if there is anything that FlexCel doesn''t support on it.'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  #</span><span style="color:#098658;--shiki-dark:#B5CEA8">$000A</span><span style="color:#A31515;--shiki-dark:#CE9178">'  2) The button "Compare with Excel" will open a file saved by Excel, recalculate it with FlexCel, compare the values reported by both FlexCel and Excel and report if there are any differences.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// This event is used when there are linked files, to load them on demand.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;param name="sender">&#x3C;/param></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;param name="e">&#x3C;/param></span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.Work_LoadLinkedFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> e: TLoadLinkedFileEventArgs);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FilePath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FilePath := TPath.Combine(TPath.GetDirectoryName(OpenDialog.FileName), e.FileName);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //IMPORTANT: DO NOT USE THIS METHOD IN PRODUCTION IF SECURITY IS IMPORTANT.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //This method will access any file in your harddisk, as long as it is linked in the spreadhseet, and</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //that could mean an IMPORTANT SECURITY RISK. You should limit the places where the app can search for</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //linked files. Look at the "Recalculating Linked Files" in the PDF API Guide for more information.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TFile.Exists(FilePath) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#008000;--shiki-dark:#6A9955">  //If we find the path, just load the file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Xls := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Xls.Open(FilePath);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //If we couldn't find the file, ask the user for its location.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LinkedFileDialog.FileName := FilePath;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LinkedFileDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#008000;--shiki-dark:#6A9955">  //if user cancels, e.Xls will be null, so no file will be used and an #errna error will show in the formulas.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  e.Xls := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Xls.Open(LinkedFileDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Xls.Free;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    e.Xls := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.ActionValidateRecalcExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Work: TWorkspace;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Usl: TUnsupportedFormulaList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FunctionStr: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // ////////Code here is only needed if you have linked files. In this example we don't know, so we will use it /////////</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Work := TWorkspace.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a workspace</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Xls.Open(OpenDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    except</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FreeAndNil(Xls);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      raise</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Work.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ExtractFileName(OpenDialog.FileName), Xls);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Add the original file to it</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Work.LoadLinkedFile:= Work_LoadLinkedFile;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Set up an event to load the linked files.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    // /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    report.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Results on file: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + OpenDialog.FileName;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Usl := Work.RecalcAndVerify;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Usl.Count = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'**********All formulas supported!**********'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Issues Found:'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Usl.Count - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Usl[i].FileName = </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName := (</span><span style="color:#A31515;--shiki-dark:#CE9178">'File: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + Usl[i].FileName) + </span><span style="color:#A31515;--shiki-dark:#CE9178">'  => '</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'     '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FileName + Usl[i].Cell.CellRef + </span><span style="color:#A31515;--shiki-dark:#CE9178">': '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + GetErrorType(Usl[i].ErrorType));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Usl[i].FunctionName &#x3C;> </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          FunctionStr := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Function'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Usl[i].ErrorType = TUnsupportedFormulaErrorType.ExternalReference </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            FunctionStr := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Linked file not found'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">' ->'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FunctionStr + </span><span style="color:#A31515;--shiki-dark:#CE9178">': '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + Usl[i].FunctionName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Usl.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Work.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.ActionCompareWithExcelExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls1: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls2: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Work: TWorkspace;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Work := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">; xls1 := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionCompareWithExcel.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionValidateRecalc.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls1 := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls2 := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        xls1.Open(OpenDialog.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        xls2.Open(openDialog.FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        report.Text := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Compare with Excel: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + OpenDialog.FileName;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">        // ////////Code here is only needed if you have linked files. In this example we don't know, so we will use it /////////</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Work := TWorkspace.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a workspace</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Work.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TPath.GetFileName(OpenDialog.FileName), xls1);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Add the original file to it</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Work.LoadLinkedFile:= Work_LoadLinkedFile;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Set up an event to load the linked files.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">         // /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        CompareXls(xls1, xls2);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        FreeAndNil(xls2);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ActionCompareWithExcel.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ActionValidateRecalc.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Work &#x3C;> </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FreeAndNil(Work) </span><span style="color:#0000FF;--shiki-dark:#569CD6">else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FreeAndNil(xls1);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.CompareXls</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls1: TXlsFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls2: TXlsFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DiffCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  sheet: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  aColCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  r: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  c: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  f: TFormula;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ad: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  f2: TFormula;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cell1: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  eps: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DiffCount := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls1.Recalc;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sheet := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls1.SheetCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls1.ActiveSheet := sheet;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls2.ActiveSheet := sheet;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    aColCount := xls1.ColCount; </span><span style="color:#008000;--shiki-dark:#6A9955">//ColCount is slow. We will calculate it only once here.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls1.RowCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> c := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aColCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      cell1 := xls1.GetCellValue(r, c);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cell1.IsFormula </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        f := cell1.AsFormula;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        ad := TCellAddress.Create(r, c);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        f2 := xls2.GetCellValue(r, c).AsFormula;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f.FormulaResult = TCellValue.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          f.FormulaResult := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f2.FormulaResult = TCellValue.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          f2.FormulaResult := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        eps := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f.FormulaResult.IsNumber and f2.FormulaResult.IsNumber </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameValue(f2.FormulaResult.AsNumber, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameValue(f.FormulaResult.AsNumber, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> eps := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            eps := f.FormulaResult.AsNumber / (f2.FormulaResult.AsNumber);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">          if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Abs(eps - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">) &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">0.001</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            f.FormulaResult := f2.FormulaResult;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f.FormulaResult &#x3C;> f2.FormulaResult </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Sheet:'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + xls1.SheetName + </span><span style="color:#A31515;--shiki-dark:#CE9178">' --- Cell:'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + ad.CellRef + </span><span style="color:#A31515;--shiki-dark:#CE9178">' --- Calculated: '</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            + f.FormulaResult.ToString + </span><span style="color:#A31515;--shiki-dark:#CE9178">'    Excel: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + f2.FormulaResult.ToString</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            + </span><span style="color:#A31515;--shiki-dark:#CE9178">'  dif: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FloatToStr(eps) + </span><span style="color:#A31515;--shiki-dark:#CE9178">'   formula: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + f.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Application.ProcessMessages;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">          Inc(DiffCount);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Finished Comparing.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DiffCount = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'**********No differences found!**********'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> report.Lines.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'  --->Found '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + IntToStr(DiffCount) + </span><span style="color:#A31515;--shiki-dark:#CE9178">' differences'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterForHDPI(Self, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFValidateRecalc.GetErrorType</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f: TUnsupportedFormulaErrorType): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  case</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TUnsupportedFormulaErrorType.FormulaTooComplex: </span><span style="color:#AF00DB;--shiki-dark:#C586C0">exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FormulaTooComplex'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TUnsupportedFormulaErrorType.MissingFunction: </span><span style="color:#AF00DB;--shiki-dark:#C586C0">exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'MissingFunction'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TUnsupportedFormulaErrorType.FunctionalityNotImplemented: </span><span style="color:#AF00DB;--shiki-dark:#C586C0">exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'FunctionalityNotImplemented'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TUnsupportedFormulaErrorType.CircularReference: </span><span style="color:#AF00DB;--shiki-dark:#C586C0">exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'CircularReference'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TUnsupportedFormulaErrorType.ExternalReference: </span><span style="color:#AF00DB;--shiki-dark:#C586C0">exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ExternalReference'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := IntToStr(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">(f));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



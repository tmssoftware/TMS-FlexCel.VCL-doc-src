---
uid: Render_Objects-Delphi
description: Render_Objects-Delphi
---


# Rendering standalone objects (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\25\.Printing and Exporting\\45\.Render Objects** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;25.&#8203;Printing and Exporting/45.Render Objects](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/25\.Printing%20and%20Exporting/45\.Render%20Objects)


## Overview


While you might normally want to render a full sheet (or a range of cells),
you can also use FlexCel to render specific objects in the workbook.

## Concepts

- This is a simple application where we periodically update a number,
  and use FlexCel to recalculate the formulas and render a chart of
  the values. While you would normally not use FlexCel this way (and
  it is probably better to use a separate chart package), it gives a
  nice tasting on FlexCel capabilities.

- How to use RenderObject to render a simple object in a sheet. In
  this demo, we are rendering the object named \"datachart\".

- As the chart and the calculations are defined in the spreadsheet,
  you can add new themes to the application or modify the existing
  ones by creating and modifying the xls files in the templates
  folders, without needing to recompile the application. You can
  even do it in real time. Have a template open in Excel, make
  changes, save, and reload the template in the application by
  selecting it again in the listbox. Changes will appear instantly
  without needing to close the main application. This technique can
  be quite useful to let users customize your application.

- In this example, we named the chart \"DataChart\", so we can
  identify it from the application. In order to name a chart object,
  ctrl-click in the chart (it should show white handles, not black),
  and then change the name in the name box at the top left in Excel.

## Files

### URenderObjects.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> URenderObjects;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Variants, Classes, Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Controls, Forms, Dialogs, ImgList, ActnList, StdCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ComCtrls, ToolWin, ExtCtrls,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render, FlexCel.Preview;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFRenderObjects = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Actions: TActionList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionRun: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionClose: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImagesDisabled: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar2: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton14: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton15: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton16: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Panel1: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Label1: TLabel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbTheme: TComboBox;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ChartBox: TImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AnimTimer: TTimer;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    PanelError: TPanel;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActionCancel: TAction;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolButton1: TToolButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImages_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImagesDisabled_100Scale: TImageList;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolbarImagesDisabled_300Scale: TImageList;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionRunExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AnimTimerTimer</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ActionCancelExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> cbThemeChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TemplatePath: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ValueRange: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    MinValue: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    MaxValue: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    StepValue: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActualValue: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ChartIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ChartProps: IShapeProperties;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> InitApp</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ReadDoubleName</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#0000FF;--shiki-dark:#569CD6"> Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> LoadFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetChart</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">override</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FRenderObjects: TFRenderObjects;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span><span style="color:#000000;--shiki-dark:#D4D4D4"> IOUtils, Types, UPaths, Math, UFlexCelHDPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">destructor</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.Destroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  inherited</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.FormCreate</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RegisterForHDPI(Self, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.ActionRunExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6"> if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    InitApp;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AnimTimer.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ActionRun.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ActionCancel.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.ActionCancelExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AnimTimer.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ActionRun.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ActionCancel.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  PanelError.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.ActionCloseExecute</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Close;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.InitApp</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fi: TStringDynArray;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  f: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TemplatePath := TPath.Combine(DataFolder, </span><span style="color:#A31515;--shiki-dark:#CE9178">'templates'</span><span style="color:#000000;--shiki-dark:#D4D4D4">) + TPath.DirectorySeparatorChar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fi := TDirectory.GetFiles(TemplatePath, </span><span style="color:#A31515;--shiki-dark:#CE9178">'*.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(fi) = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Sorry, no templates found in the templates folder.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbTheme.Items.Clear;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> f </span><span style="color:#0000FF;--shiki-dark:#569CD6">in</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fi </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cbTheme.Items.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Add</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TPath.GetFileName(f));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cbTheme.ItemIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LoadFile(fi[</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">]);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.ReadDoubleName</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#0000FF;--shiki-dark:#569CD6"> Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Range: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  val: TCellValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Range := Xls.GetNamedRange(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Range.IsNull </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create((</span><span style="color:#A31515;--shiki-dark:#CE9178">'There is no range named '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">) + </span><span style="color:#A31515;--shiki-dark:#CE9178">' in the template'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  val := Xls.GetCellValue(Range.Top, Range.Left);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (val.IsNumber) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create((</span><span style="color:#A31515;--shiki-dark:#CE9178">'The range named '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">) + </span><span style="color:#A31515;--shiki-dark:#CE9178">' does not contain a number'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := val.AsNumber;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.LoadFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ObjName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Open(FileName);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ActualValue := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ValueRange := Xls.GetNamedRange(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Value'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ValueRange.IsNull </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'There is no range named "value" in the template'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MinValue := ReadDoubleName(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Minimum'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MaxValue := ReadDoubleName(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Maximum'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  StepValue := ReadDoubleName(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Step'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartIndex := -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls.ObjectCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ObjName := Xls.GetObjectName(i);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SameText(ObjName, </span><span style="color:#A31515;--shiki-dark:#CE9178">'DataChart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ChartIndex := i;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      break</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ChartIndex &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    raise</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Exception.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'There is no object named "DataChart" in the template'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartProps := Xls.GetObjectProperties(ChartIndex, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.AnimTimerTimer</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ActualValue:= ActualValue + StepValue;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ActualValue > MaxValue </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ActualValue := MinValue;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetCellValue(ValueRange.Top, ValueRange.Left, ActualValue);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.Recalc;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    GetChart;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  except</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //We don't want any dialog popping up every second.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    on</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ex: Exception </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        PanelError.Caption := ex.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Message</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        PanelError.Align := alClient;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        PanelError.Visible := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        AnimTimer.Enabled := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.cbThemeChange</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (cbTheme.ItemIndex &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">			LoadFile(TPath.Combine(TemplatePath, cbTheme.Items[cbTheme.ItemIndex]));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFRenderObjects.GetChart</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImageDimensions: TUIRectangle;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Origin: TUIPointF;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SizePixels: TUISize;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dpi: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AspectX: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AspectY: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Aspect: RealNumber;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Img: TUIImage;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //We could get the chart with the following command,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //but it would be fixed size. In this example we are going to be a little more complex.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Xls.RenderObject(ChartIndex);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //A more complex way to retrieve the chart, to show how to use</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //all parameters in renderobject.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //First calculate the chart dimensions without actually rendering it. This is fast.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.RenderObject(ChartIndex, Font.PixelsPerInch, ChartProps, TUISmoothingMode.AntiAlias, TUIInterpolationMode.HighQualityBicubic, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Origin, ImageDimensions, SizePixels);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dpi := Font.PixelsPerInch;  </span><span style="color:#008000;--shiki-dark:#6A9955">//default screen resolution</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Aspect := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (SizePixels.Height > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) and (SizePixels.Width > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AspectX := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1.0</span><span style="color:#000000;--shiki-dark:#D4D4D4"> * chartBox.Width / SizePixels.Width;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AspectY := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1.0</span><span style="color:#000000;--shiki-dark:#D4D4D4"> * chartBox.Height / SizePixels.Height;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Aspect := Min(AspectX, AspectY);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Make the dpi adjust the screen resolution and the size of the form.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    dpi := Font.PixelsPerInch * Aspect;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> dpi &#x3C; </span><span style="color:#098658;--shiki-dark:#B5CEA8">20</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      dpi := </span><span style="color:#098658;--shiki-dark:#B5CEA8">20</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> dpi > </span><span style="color:#098658;--shiki-dark:#B5CEA8">500</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      dpi := </span><span style="color:#098658;--shiki-dark:#B5CEA8">500</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Img := Xls.RenderObject(ChartIndex, dpi, ChartProps, TUISmoothingMode.AntiAlias, TUIInterpolationMode.HighQualityBicubic, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Origin, ImageDimensions, SizePixels);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (ChartBox.Picture.Width &#x3C;> ChartBox.Width) or (ChartBox.Picture.Height &#x3C;> ChartBox.Height)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">        then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ChartBox.Picture := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Img.ToNativeImage(</span><span style="color:#0000FF;--shiki-dark:#569CD6">Pointer</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ChartBox.Canvas.Handle), Aspect);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Invalidate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Img.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



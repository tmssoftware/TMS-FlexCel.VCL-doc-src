---
uid: Reading_Files-FireMonkey_Desktop
description: Reading_Files-FireMonkey_Desktop
---


# Reading Excel files (FireMonkey Desktop)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\FireMonkey Desktop\\Modules\\20\.Reading Files** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Fire&#8203;Monkey Desktop/&#8203;Modules/&#8203;20.&#8203;Reading Files](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/FireMonkey%20Desktop/Modules/20\.Reading%20Files)


## Overview


A demo showing how to read the contents of an Excel file using FlexCel.

## Concepts

- To read an Excel file you use the [TXlsFile](~/api/FlexCel.XlsAdapter/TXlsFile/index.md) class, from where you
  can read and write to any Excel 2.0 or newer
  file.

- To get the value for a single cell, use [TXlsFile.GetCellValue](~/api/FlexCel.XlsAdapter/TXlsFile/GetCellValue.md).

- To get the value for a cell when looping a full sheet, use
  [TXlsFile.GetCellValueIndexed](~/api/FlexCel.XlsAdapter/TXlsFile/GetCellValueIndexed.md). It is faster than using
  GetCellValue since you will only read the used cells.


- [TXlsFile.GetCellValue](~/api/FlexCel.XlsAdapter/TXlsFile/GetCellValue.md) and 
[TXlsFile.GetCellValueIndexed](~/api/FlexCel.XlsAdapter/TXlsFile/GetCellValueIndexed.md) will return a 
TCellValue that will be one of the objects allowed in an Excel cell

- With GetCellValue and GetCellValueIndexed you will get the actual
  values. But if you want to actually display formatted data (for
  example if you have the number 2 with 2 decimals, and you want to
  display 2.00 instead of 2), you need to use other methods. There
  are 2 ways to do it:

   1. [TXlsFile.GetStringFromCell](~/api/FlexCel.XlsAdapter/TXlsFile/GetStringFromCell.md) will return a rich string with the
   cell formatted.

   2. FormatValue will format an object with a
   specified format and then return the corresponding rich string.
   TFlxNumberFormat.FormatValue is used internally by
   GetStringFromCell.

- In Excel, **Dates are doubles**. The only difference between a date
  and a double is on the format on the cell. With
  FormatValue you can get the actual string that is
  displayed on Excel. Also, to convert this double to a DateTime,
  you can use [TFlxDateTime.FromOADate](~/api/FlexCel.Core/TFlxDateTime/FromOADate.md).

## Files

### UReadingFiles.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UReadingFiles;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, System.Types, System.UITypes, System.Classes, System.Variants,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.Types, FMX.StdCtrls, FMX.Controls, FMX.Forms, FMX.Dialogs, FMX.Layouts, FMX.Grid,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.TabControl, FMX.Objects, System.Math, System.Rtti,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion &#x3C; 31.0}{$else}</span><span style="color:#000000;--shiki-dark:#D4D4D4">FMX.Grid.Style, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.FMXSupport, FlexCel.Core, FlexCel.XlsAdapter, FMX.Edit, FMX.Graphics,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.ScrollBox, FMX.Controls.Presentation;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFReadingFiles = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ToolBar1: TToolBar;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenDialog: TOpenDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnOpen: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SheetData: TGrid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Image1: TImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnFormatValues: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Image2: TImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnInfo: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Image4: TImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Tabs: TTabControl;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnInfoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnOpenClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SheetDataGetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Col, Row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      var</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TValue);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnFormatValuesClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FormDestroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SheetDataDrawColumnCell</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Canvas: TCanvas;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Column: TColumn; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Bounds: TRectF; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TValue; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> State: TGridDrawStates);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ClearGrid</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SetupGrid</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ImportFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> FillTabs</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> SheetChanged</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FReadingFiles: TFReadingFiles;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.fmx}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.btnFormatValuesClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SheetData.Repaint; </span><span style="color:#008000;--shiki-dark:#6A9955">//when repainting, we will read the new value of this button.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.btnInfoClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShowMessage(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This demo shows how to read the contents of an xls file'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#A31515;--shiki-dark:#CE9178">#10</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">      'The ''Open File'' button will load an Excel file into a dataset.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">+ </span><span style="color:#A31515;--shiki-dark:#CE9178">#10</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">      'The ''Format Values'' button will apply the format to the cells, or show the raw data.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">+ </span><span style="color:#A31515;--shiki-dark:#CE9178">#10</span><span style="color:#000000;--shiki-dark:#D4D4D4"> +</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">      'The ''Value in Current Cell'' button will show more information about the cell selected in the grid. Try it with formulas.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.btnOpenClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> OpenDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ImportFile(OpenDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.ImportFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> FileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Open the Excel file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Open(FileName);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FillTabs;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetupGrid;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Caption := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Reading Files: '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + ExtractFileName(FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.SheetChanged</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.ActiveSheet := (Sender </span><span style="color:#0000FF;--shiki-dark:#569CD6">as</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TComponent).Tag;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetupGrid;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.SheetDataDrawColumnCell</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Canvas: TCanvas; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Column: TColumn; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Bounds: TRectF;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TValue; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> State: TGridDrawStates);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FillBrush: TBrush;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  BoundsExt: TRectF;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Here we will show how to do colors</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   BoundsExt := Bounds;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   BoundsExt.Inflate(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   fmt := Xls.GetCellVisibleFormatDef(Row + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Column.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (fmt.FillPattern.Pattern = TFlxPatternStyle.Solid) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      FillBrush := TBrush.Create(TBrushKind.Solid, fmt.FillPattern.FgColor.ToColor(xls));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        Canvas.FillRect(BoundsExt, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, FillBrush);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        FillBrush.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Canvas.Font.Size := fmt.Font.Size20 / </span><span style="color:#098658;--shiki-dark:#B5CEA8">20.0</span><span style="color:#000000;--shiki-dark:#D4D4D4"> * </span><span style="color:#098658;--shiki-dark:#B5CEA8">96.0</span><span style="color:#000000;--shiki-dark:#D4D4D4">/ </span><span style="color:#098658;--shiki-dark:#B5CEA8">72.0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Firemonkey's Font.size is smaller than in VCL. So we multiply by 96/72.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Canvas.Font.Family := fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">      //You could assign the font style here too.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Canvas.Fill.Color := fmt.Font.Color.ToColor(xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Canvas.FillText(Bounds, Xls.GetStringFromCell(Row + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Column.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Index</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToString,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">         fmt.WrapText, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, [], TTextAlign.Leading);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">   end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.SheetDataGetValue</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Col,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">var</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Value: TValue);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls = </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Value := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> btnFormatValues.IsPressed </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    value := Xls.GetStringFromCell(Row + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Col + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToString;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    value := Xls.GetCellValue(Row + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Col + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.FillTabs</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  s, i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  btn: TTabItem;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := Tabs.TabCount - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> downto</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Tabs.Tabs[i].Free;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> s := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls.SheetCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btn := TTabItem.Create(Tabs);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btn.Text := Xls.GetSheetName(s);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btn.Tag := s;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btn.OnClick := SheetChanged;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Tabs.AddObject(btn);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.FormDestroy</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.ClearGrid</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SheetData.RowCount := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := SheetData.ColumnCount - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> downto</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 0</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SheetData.Columns[i].Free;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFReadingFiles.SetupGrid</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Column: TColumn;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  c: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SheetData.BeginUpdate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ClearGrid;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SheetData.RowCount := Xls.RowCount;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ColCount := Xls.ColCount; </span><span style="color:#008000;--shiki-dark:#6A9955">// NOTE THAT COLCOUNT IS SLOW. We use it here because we really need it. See the Performance.pdf doc.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    //Create the columns</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> c := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ColCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Column := TColumn.Create(SheetData);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Column.Width := Xls.GetColWidth(c) / TExcelMetrics.ColMult(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Column.Header := TCellAddress.EncodeColumn(c);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Column.Parent := SheetData;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SheetData.EndUpdate;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SheetData.Repaint;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



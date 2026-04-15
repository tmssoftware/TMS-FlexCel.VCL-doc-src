---
uid: GettingStarted-FireMonkey_Desktop
description: GettingStarted-FireMonkey_Desktop
---


# Getting started (FireMonkey Desktop)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\FireMonkey Desktop\\Modules\\10\.GettingStarted** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Fire&#8203;Monkey Desktop/&#8203;Modules/&#8203;10.&#8203;Getting&#8203;Started](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/FireMonkey%20Desktop/Modules/10\.GettingStarted)


## Overview


A simple demo showing how to create an Excel file with the API from scratch.

## Concepts


- Before using FlexCel, you have to add
  \"**uses FlexCel.VCLSupport**\", \"**uses FlexCel.Core**\" and \"**uses FlexCel.XlsAdapter**\" to
  your uses statements. 
  For a FireMonkey app, you would add \"**uses FlexCel.FMXSupport**\"
  instead of \"**uses FlexCel.VCLSupport**\"
 You need to use FMXSupport/VCLSupport units once in your app, so FlexCel can initialize the correct graphics engine. There is no need to add them more than once.

- The most important class here is the [TXlsFile](~/api/FlexCel.XlsAdapter/TXlsFile/index.md) class, from where
  you can read and write to any Excel 2 or newer file.

- To set the value for a cell, use [TXlsFile.SetCellValue](~/api/FlexCel.XlsAdapter/TXlsFile/SetCellValue.md). You can
  set any kind of object here, not just text. If you set it to
  a [TFormula](~/api/FlexCel.Core/TFormula/index.md) object, you will enter a formula.

- As explained in the [FlexCel API Developer Guide](~/guides/api-developer-guide.md), formats in Excel are indexes to an XF (e**X**tended **F**ormat list) 
  To modify the format on a cell, you have to assign an XF index to
  that cell. To create new XF formats, use [TXlsFile.AddFormat](~/api/FlexCel.XlsAdapter/TXlsFile/AddFormat.md)

## Files

### UGettingStarted.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UGettingStarted;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  System.SysUtils, System.Types, System.UITypes, System.Classes, System.Variants,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.Types, FMX.StdCtrls, FMX.Controls, FMX.Forms, FMX.Dialogs,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$if CompilerVersion >= 31}</span><span style="color:#008000;--shiki-dark:#6A9955">  //Delphi 10.1 Berlin deprecated MessageDlg</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.DialogService.Sync,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$endif}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FlexCel.FMXSupport, FlexCel.Core, FlexCel.XlsAdapter, FMX.FlexCel.DocExport,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FMX.Controls.Presentation;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFGettingStarted = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    BtnCreateFile: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DocExport: TFlexCelDocExport;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> ShowOpenDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Private declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  public</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">    { Public declarations }</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FGettingStarted: TFGettingStarted;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.fmx}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFGettingStarted.CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AddData(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShowOpenDialog(Xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(Xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFGettingStarted.AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Img: TResourceStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF, XF2: </span><span style="color:#0000FF;--shiki-dark:#569CD6">integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Create a new file. We could also open an existing file with Xls.Open</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2019);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Set some cell values.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Hello to the world'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2.1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=Sum(A2, A3)'</span><span style="color:#000000;--shiki-dark:#D4D4D4">)); </span><span style="color:#008000;--shiki-dark:#6A9955">//Note that formulas always are in English. This means use "," to separate arguments, not ";".</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Add a new image on cell F2</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Img := TResourceStream.Create(hinstance, </span><span style="color:#A31515;--shiki-dark:#CE9178">'FlexCelLogo'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, RT_RCDATA);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.AddImage(Img,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TImageProperties_Create(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TClientAnchor.Create(TFlxAnchorType.MoveAndResize, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">8</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">),</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">    ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'My image'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Img.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Add a comment on cell a2</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Xls.SetComment(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is a comment'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Custom Format cells a2 and a3</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt := Xls.GetDefaultFormat;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Always initialize the record with an existing format.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Times New Roman'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Font.Color := TColorRec.Red;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.FillPattern.Pattern := TFlxPatternStyle.LightDown;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.FillPattern.FgColor := TColorRec.Blue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.FillPattern.BgColor := TColorRec.White;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//You can call AddFormat as many times as you want, it will never add a format twice.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//But if you know the format you are going to use, you can get some extra CPU cycles by</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//calling addformat once and saving the result into a variable.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	XF := Xls.AddFormat(fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	fmt.Rotation := </span><span style="color:#098658;--shiki-dark:#B5CEA8">45</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Font.Size20 := </span><span style="color:#098658;--shiki-dark:#B5CEA8">400</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF2 := Xls.AddFormat(fmt);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Apply a custom format to all the row.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Xls.SetRowFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, XF2);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Merge cells</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Xls.MergeCells(</span><span style="color:#098658;--shiki-dark:#B5CEA8">5</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Note how this one merges with the previous range, creating a final range (5,1,15,6)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Xls.MergeCells(</span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">15</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">6</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">	//Make the page print in landscape or portrait mode</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Xls.PrintLandscape := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFGettingStarted.btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  CreateFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFGettingStarted.ShowOpenDialog</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Save(SaveDialog.FileName); </span><span style="color:#008000;--shiki-dark:#6A9955">//No need to delete the file first, since AllowOverWriteFiles is true in XlsAdapter.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$if CompilerVersion >= 31}</span><span style="color:#008000;--shiki-dark:#6A9955">  //Delphi 10.1 Berlin deprecated MessageDlg</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> TDialogServiceSync.MessageDialog(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TMsgDlgType.mtConfirmation, [TMsgDlgBtn.mbYes, TMsgDlgBtn.mbNo], TMsgDlgBtn.mbYes, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DocExport.ExportFile(</span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SaveDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$else}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TMsgDlgType.mtConfirmation, [TMsgDlgBtn.mbYes, TMsgDlgBtn.mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    DocExport.ExportFile(</span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SaveDialog.FileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$endif}</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



---
uid: Advanced_API-Delphi
description: Advanced_API-Delphi
---


# Advanced API (Delphi)

> [!Note]
> This demo is available in your FlexCel installation at ***&lt;FlexCel Install Folder>*\\Demo\\Delphi\\Modules\\10\.API\\12\.Advanced API** and also at [https:&#8203;//&#8203;github.&#8203;com/&#8203;tmssoftware/&#8203;TMS-&#8203;FlexCel.&#8203;VCL-&#8203;demos/&#8203;tree/&#8203;master/&#8203;Delphi/&#8203;Modules/&#8203;10.&#8203;API/&#8203;12.&#8203;Advanced API](https://github\.com/tmssoftware/TMS\-FlexCel\.VCL\-demos/tree/master/Delphi/Modules/10\.API/12\.Advanced%20API)


## Overview


This demo shows a lot of unrelated things you can do with the FlexCel
API.

It is a **complement** of what was shown in [GettingStarted](~/samples/delphi/api/gettingstarted/index.md): this
means things that were shown there (like how to insert an image)
will not be repeated here. You should look at both demos when studying the
API.

The things shown here do not make much sense in the real world; they are
explicitly designed to show what can be done. 

Also remember that most of
this stuff can be found easier with APIMate


The created file will be password protected, and all the passwords are
\"**flexcel**\" (without quotes)

## Concepts

- FlexCel shines at modifying existing Excel files. It has been
  designed from the start with that in mind, and to not losing
  anything in the original file. So we will
  start from an existing file with the skeleton of what we want to
  do, and modify it with code. 
  This starting file (template.xls/x)
  could be embedded in the exe file, but this is not shown here. 
  To see an example on how to embed the template inside the exe, look at
  [Templates In The Exe](~/samples/delphi/reports/templates-in-the-exe/index.md)

- The starting template has a macro. At this time we can not create
  macros with FlexCel, but we can modify a file with existing macros
  and those macros will be in the final file.

- How to copy a chart from other template and fill the values.

- How to add Outlines.

- How to freeze panes.

- How to add data validation.

- How to search and replace in a range of cells.

- How to sort a range of cells.

- How to Autofit the rows in a sheet.

- How to protect the file and cells with a password.

- As FlexCel doesn\'t convert charts between xlsx and xls, if you want
  to create an xls file you need to start with an xls template, and
  the same goes for xlsx. So we need two templates.

## Files

### UAdvancedAPI.pas

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">unit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> UAdvancedAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">interface</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">uses</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Windows, Messages, SysUtils, Classes, Graphics, Controls, Forms, UPaths,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Dialogs, StdCtrls, FlexCel.VCLSupport, FlexCel.Core, FlexCel.XlsAdapter, FlexCel.Render,</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">  {$if CompilerVersion >= 23.0}</span><span style="color:#000000;--shiki-dark:#D4D4D4"> System.UITypes, </span><span style="color:#811F3F;--shiki-dark:#D16969">{$IFEND}</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ShellAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">type</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  TFAdvancedAPI = </span><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#000000;--shiki-dark:#D4D4D4">(TForm)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Memo1: TMemo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnCreateFile: TButton;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SaveDialog: TSaveDialog;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    btnUseXlsx: TCheckBox;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  private</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AddChart</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataCell: TXlsNamedRange; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetCountryList</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FAdvancedAPI: TFAdvancedAPI;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">implementation</span></span>
<span class="line"></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$IFNDEF FPC}</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$R *.dfm}</span></span>
<span class="line"><span style="color:#811F3F;--shiki-dark:#D16969">{$ENDIF}</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //some silly data to fill in the cells. A real app would read this from somewhere else.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	Country: </span><span style="color:#0000FF;--shiki-dark:#569CD6">array</span><span style="color:#000000;--shiki-dark:#D4D4D4"> [</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span><span style="color:#098658;--shiki-dark:#B5CEA8">.7</span><span style="color:#000000;--shiki-dark:#D4D4D4">] </span><span style="color:#0000FF;--shiki-dark:#569CD6">of</span><span style="color:#0000FF;--shiki-dark:#569CD6"> string</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = (</span><span style="color:#A31515;--shiki-dark:#CE9178">'USA'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Canada'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Spain'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'France'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'United Kingdom'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Australia'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Brazil'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Unknown'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">	DataRows = </span><span style="color:#098658;--shiki-dark:#B5CEA8">100</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;summary></span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// Will return a list of countries separated by Character(0) so it can be used as input for a built in list.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">/// &#x3C;/summary></span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.GetCountryList</span><span style="color:#000000;--shiki-dark:#D4D4D4">: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  sep: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  c: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Integer</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  sep := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> fIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(Country) - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      c := Country[fIndex];</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#0000FF;--shiki-dark:#569CD6">Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + sep + c;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      sep := </span><span style="color:#A31515;--shiki-dark:#CE9178">#0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//not very efficient method to concat, but good enough for this demo.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.AddChart</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataCell: TXlsNamedRange; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartRange: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FirstCell: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SecondCell: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FirstSumCell: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  r: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Find the cell where the cart will go.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartRange := Xls.GetNamedRange(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ChartData'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Insert cells to expand the range for the chart. It already has 2 rows, so we need to insert Country.Length - 2</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Note also that we insert after ChartRange.Top, so the chart is updates with the new range.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.InsertAndCopyRange(TXlsCellRange.Create(ChartRange.Top, ChartRange.Left, ChartRange.Top, ChartRange.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">), ChartRange.Top + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, ChartRange.Left, Length(Country) - </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFlxInsertMode.ShiftRangeDown);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //we use shiftrangedown so not all the row goes down and the chart stays in place.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Get the cell addresses of the data range.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FirstCell := TCellAddress.Create(DataCell.Top, DataCell.Left);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SecondCell := TCellAddress.Create(DataCell.Top + DataRows, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  FirstSumCell := TCellAddress.Create(DataCell.Top, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Fill a table with the data to be used in the chart.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r := ChartRange.Top </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> ChartRange.Top + Length(Country) - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetCellValue(r, ChartRange.Left, Country[r - ChartRange.Top]);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetCellValue(r, ChartRange.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=SUMIF('</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FirstCell.CellRef + </span><span style="color:#A31515;--shiki-dark:#CE9178">':'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + SecondCell.CellRef</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      + </span><span style="color:#A31515;--shiki-dark:#CE9178">',"'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + Country[r - ChartRange.Top] + </span><span style="color:#A31515;--shiki-dark:#CE9178">'", '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + FirstSumCell.CellRef</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      + </span><span style="color:#A31515;--shiki-dark:#CE9178">':'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + SecondCell.CellRef + </span><span style="color:#A31515;--shiki-dark:#CE9178">')'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.AddData</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DataCell: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ApplyFormat: TFlxApplyFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  z: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OutlineLevel: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  r: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dv: TDataValidationInfo;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartRange: TXlsNamedRange;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Sp: TSheetProtectionOptions;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Template: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Keys: Int32Array;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SortOrder: TArray&#x3C;TSortOrder>;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> btnUseXlsx.Checked </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Template := </span><span style="color:#A31515;--shiki-dark:#CE9178">'AdvancedAPI.template.xlsm'</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Template := </span><span style="color:#A31515;--shiki-dark:#CE9178">'AdvancedAPI.template.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // Open an existing file to be used as template. In this example this file has</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // little data, in a real situation it should have as much as possible. (Or even better, be a report)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Open(DataFolder + Template);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Find the cell where we want to fill the data. In this case, we have created a named range "data" so the address</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //is not hardcoded here.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  DataCell := Xls.GetNamedRange(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Data'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Add a chart with totals</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  AddChart(DataCell, Xls);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Note that "DataCell" will change because we inserted rows above it when creating the chart. But we will keep using the old one.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Add the captions. This should probably go into the template, but in a dynamic environment it might go here.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(DataCell.Top - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DataCell.Left, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Country'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellValue(DataCell.Top - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Quantity'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Add a rectangle around the cells</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ApplyFormat := TFlxApplyFormat.Create;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ApplyFormat.SetAllMembers(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ApplyFormat.Borders.SetAllMembers(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//We will only apply the borders to the existing cell formats</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt := Xls.GetDefaultFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Borders.Left.Style := TFlxBorderStyle.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Borders.Right.Style := TFlxBorderStyle.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Borders.Top.Style := TFlxBorderStyle.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt.Borders.Bottom.Style := TFlxBorderStyle.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Double</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SetCellFormat(DataCell.Top - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DataCell.Left, DataCell.Top, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, fmt, ApplyFormat, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Set last parameter to true so it draws a box.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Freeze panes</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.FreezePanes(TCellAddress.Create(DataCell.Top, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Randomize;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  z := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Fill the data</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  OutlineLevel := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> r := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> DataRows </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Fill the values.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetCellValue(DataCell.Top + r, DataCell.Left, Country[z </span><span style="color:#0000FF;--shiki-dark:#569CD6">mod</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(Country)]);  </span><span style="color:#008000;--shiki-dark:#6A9955">//For non C# users, "%" means "mod" or modulus in other languages. It is the rest of the integer division.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetCellValue(DataCell.Top + r, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Random(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1000</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //Add the country to the outline</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Xls.SetRowOutlineLevel(DataCell.Top + r, OutlineLevel);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //increment the country randomly</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Random(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Inc(z);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      OutlineLevel := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Break the group and create a new one.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      OutlineLevel := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Make the "+" signs of the outline appear at the top.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.OutlineSummaryRowsBelowDetail := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Collapse the outline to the first level.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.CollapseOutlineRows(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TCollapseChildrenMode.Collapsed);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Add Data Validation for the first column, it must be a country.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dv := TDataValidationInfo.Create(TDataValidationDataType.List,  </span><span style="color:#008000;--shiki-dark:#6A9955">//We will use a built in list.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">           TDataValidationConditionType.Between, </span><span style="color:#008000;--shiki-dark:#6A9955">//This parameter does not matter since it is a list. It will not be used.</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           '="'</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + GetCountryList + </span><span style="color:#A31515;--shiki-dark:#CE9178">'"'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,  </span><span style="color:#008000;--shiki-dark:#6A9955">//We could have used a range of cells here with the values (like "=C1..C4") Instead, we directly entered the list in the formula.</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">,  </span><span style="color:#008000;--shiki-dark:#6A9955">//no need for a second formula, not used in List</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">           false</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">           true</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">           true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//Note that as we entered the data directly in FirstFormula, we need to set this to true</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">           true</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           'Unknown country'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           'Please make sure that the country is in the list'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">           false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//We will not use an input box, so this is false and the 2 next entries are nil</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">           ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">           TDataValidationIcon.Stop); </span><span style="color:#008000;--shiki-dark:#6A9955">//We will use the stop icon so no invalid input is permitted.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.AddDataValidation(TXlsCellRange.Create(DataCell.Top, DataCell.Left, DataCell.Top + DataRows, DataCell.Left), dv);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Add Data Validation for the second column, it must be an integer between 0 and 1000.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  dv := TDataValidationInfo.Create(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            TDataValidationDataType.WholeNumber, </span><span style="color:#008000;--shiki-dark:#6A9955">//We will request a number.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            TDataValidationConditionType.Between,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            '=0'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//First formula marks the first part of the "between" condition.</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            '=1000'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//Second formula is the second part.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            false</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            false</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            false</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            true</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            'Invalid Quantity'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            ''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//We will leave the default error message.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">            true</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            'Quantity:'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#A31515;--shiki-dark:#CE9178">            'Please enter a quantity between 0 and 1000'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">            TDataValidationIcon.Stop); </span><span style="color:#008000;--shiki-dark:#6A9955">//We will use the stop icon so no invalid input is permitted.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.AddDataValidation(TXlsCellRange.Create(DataCell.Top, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, DataCell.Top + DataRows, DataCell.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">), dv);</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Search country "Unknown" and replace it by "no".</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //This does not make any sense here (we could just have entered "no" to begin)</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //but it shows how to do it when modifying an existing file</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   Xls.Replace(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Unknown'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'no'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsCellRange.FullRange, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Autofit the rows. As we keep the row height automatic this will not show when opening in Excel, but will work when directly printing from FlexCel.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   Xls.AutofitRowsOnWorkbook(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Recalc;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Calculate the SUMIF formulas so we can sort by them. Note that FlexCel automatically recalculates before saving,</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">               //but in this case we haven't saved yet, so the sheet is not recalculated. You do not normally need to call Recalc directly.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Sort the data. As in the case with replace, this does not make much sense. We could have entered the data sorted to begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //But it shows how you can use the feature.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Find the cell where the chart goes.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ChartRange := Xls.GetNamedRange(</span><span style="color:#A31515;--shiki-dark:#CE9178">'ChartData'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Keys := Int32Array.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SortOrder := TArray&#x3C;TSortOrder>.Create(TSortOrder.Descending);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Sort(TXlsCellRange.Create(ChartRange.Top, ChartRange.Left, ChartRange.Top + Length(Country),</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   ChartRange.Left + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Keys, SortOrder, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Protect the Sheet</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Sp := TSheetProtectionOptions.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create default protection options that allows everything.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Sp.InsertColumns := </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//Restrict inserting columns.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Protection.SetSheetProtection(</span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Sp);</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Set a modify password. Note that this does *not* encrypt the file.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Protection.SetModifyPassword(</span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Protection.OpenPassword := </span><span style="color:#A31515;--shiki-dark:#CE9178">'flexcel'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//OpenPasword is the only password that will actually encrypt the file, so you will not be able to open it with flexcel if you do not know the password.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //Select cell A1</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.SelectCell(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.btnCreateFileClick</span><span style="color:#000000;--shiki-dark:#D4D4D4">(Sender: TObject);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   CreateFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.CreateFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls: TExcelFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AddData(Xls);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    OpenFile(Xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    FreeAndNil(Xls);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> TFAdvancedAPI.OpenFile</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Xls: TExcelFile);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#0000FF;--shiki-dark:#569CD6"> not</span><span style="color:#000000;--shiki-dark:#D4D4D4"> SaveDialog.Execute </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Xls.Save(SaveDialog.FileName); </span><span style="color:#008000;--shiki-dark:#6A9955">//No need to delete the file first, since AllowOverWriteFiles is true in XlsAdapter.</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> MessageDlg(</span><span style="color:#A31515;--shiki-dark:#CE9178">'Do you want to open the generated file?'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, mtConfirmation, [mbYes, mbNo], </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) = mrYes </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ShellExecute(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'open'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">PCHAR</span><span style="color:#000000;--shiki-dark:#D4D4D4">(SaveDialog.FileName), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, SW_SHOWNORMAL);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">.</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>



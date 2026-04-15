---
uid: TExcelMetrics
description: TExcelMetrics
---

# TExcelMetrics Record

Returns Information to convert between standard units and Excel units\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TExcelMetrics = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetFont0Width](GetFont0Width.md)|**Overloaded<br />**  [GetFont0Width\(IRowColSize\)](GetFont0Width.md#texcelmetricsgetfont0widthirowcolsize)<br />  [GetFont0Width\(IRowColSize, Boolean\)](GetFont0Width.md#texcelmetricsgetfont0widthirowcolsize-boolean)<br />|
|[GetFont0SpaceWidth](GetFont0SpaceWidth.md)|Returns the width of a space \(" "\) in the main font of the workbook\.<br />|
|[GetRowHeightInPixels](GetRowHeightInPixels.md)|Returns the Height of an XF format Excel\.<br />|
|[FmlaMult](FmlaMult.md)|When showing/printing the sheet and "Show formula" check box is on, column widths are double of the normal ones\.<br />This method returns 0\.5 when "Show formulas" is turned on, and 1 if it is not\.<br />|
|[ColMultDisplay](ColMultDisplay.md)|Multiply by this number to convert the width of a column from GraphicsUnit\.&#8203;Display units \(1/100 inch\)  to Excel internal units\. Note that the default column width is different, you need to multiply by [DefColWidthAdapt](DefColWidthAdapt.md) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|
|[RowMultDisplay](RowMultDisplay.md)|Multiply by this number to convert the height of a row from GraphicsUnit\.&#8203;Display units \(1/100 inch\)  to Excel internal units\.<br />See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|
|[ColMult](ColMult.md)|Multiply by this number to convert the width of a column from resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\) to excel internal units\.<br />Note that the default column width is different, you need to multiply by [DefColWidthAdapt](DefColWidthAdapt.md) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|
|[DefColWidthAdapt](DefColWidthAdapt.md)|Convert the DEFAULT column width to resolution\-&#8203;independent\-&#8203;pixels \(1/96 of an inch\)\. This is different from [ColMult](ColMult.md), that goes in a column by column basis\.<br />See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|



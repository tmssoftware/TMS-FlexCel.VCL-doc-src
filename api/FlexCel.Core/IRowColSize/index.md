---
uid: IRowColSize
description: IRowColSize
---

# IRowColSize Interface

Interface for row heights and columns widths\. XlsFile implements this interface, so you can pass an XlsFile object anytime you need to pass this interface\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IRowColSize = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[DefaultRowHeight&#8203;Visual](DefaultRowHeightVisual.md)|The default height for empty rows, in Excel internal units\. \(1/20th of a point\)\. Different from [TExcelFile.&#8203;Default&#8203;RowHeight](../TExcelFile/DefaultRowHeight.md) this property returns the actual row height as Excel will show it, considering [TExcelFile.&#8203;Default&#8203;RowHidden](../TExcelFile/DefaultRowHidden.md) and [TExcelFile.&#8203;Default&#8203;RowHeight&#8203;Automatic](../TExcelFile/DefaultRowHeightAutomatic.md)\.<br />See [Excel Internal Units](xref:ExcelInternalUnits)[...[more]](DefaultRowHeightVisual.md)|
|[IsEmptyRow](IsEmptyRow.md)|True if the specified row does not have any cells, nor any format on it\.<br />In short, this row has never been used\.<br />|
|[GetRowHeight](GetRowHeight.md)|Returns the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|
|[GetColWidth](GetColWidth.md)|Returns the current Column width, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.<br />|
|[GetCachedFont0](GetCachedFont0.md)|This method is used by FlexCel itself, you shouldn't call it directly\.<br />|
|[SetCachedFont0](SetCachedFont0.md)|This method is used by FlexCel itself, you shouldn't call it directly\.<br />|



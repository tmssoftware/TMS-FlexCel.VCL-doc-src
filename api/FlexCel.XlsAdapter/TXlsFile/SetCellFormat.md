---
uid: TXlsFile.SetCellFormat
description: TXlsFile.SetCellFormat
---

# TXlsFile\.SetCellFormat Method

## Overloads

* [TXlsFile\.SetCellFormat\(Integer, Integer, Integer\)](#txlsfilesetcellformatinteger-integer-integer)
* [TXlsFile\.SetCellFormat\(Integer, Integer, Integer, Integer, Integer\)](#txlsfilesetcellformatinteger-integer-integer-integer-integer)
* [TXlsFile\.SetCellFormat\(Integer, Integer, Integer, Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](#txlsfilesetcellformatinteger-integer-integer-integer-tflxformat-tflxapplyformat-boolean)

# TXlsFile\.SetCellFormat\(Integer, Integer, Integer\)
Sets the Cell format \(XF\) on a given cell\.
You can create new formats using the  [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellFormat(const row: Integer; const col: Integer; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index of the cell \(1 based\)|
|const|**col**|Integer|Column index of the cell \(1 based\)|
|const|**XF**|Integer|XF Format index\. See ['Cell formats' in the Api Developer Guide](xref:ApiDeveloperGuide#cell-formats)\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.GetCellFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md)

# TXlsFile\.SetCellFormat\(Integer, Integer, Integer, Integer, Integer\)
Sets the Cell format \(XF\) on a range of cells\.
You can create new formats using the  [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md) function\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellFormat(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const XF: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Row index of the top cell on the range \(1 based\)|
|const|**col1**|Integer|Column index of the left cell on the range \(1 based\)|
|const|**row2**|Integer|Row index of the bottom cell on the range \(1 based\)|
|const|**col2**|Integer|Column index of the right cell on the range \(1 based\)|
|const|**XF**|Integer|XF Format index\. See ['Cell formats' in the Api Developer Guide](xref:ApiDeveloperGuide#cell-formats)\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.GetCellFormat\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetCellFormat.md#texcelfilegetcellformatinteger-integer)
* [TExcelFile.AddFormat](../../FlexCel.Core/TExcelFile/AddFormat.md)

# TXlsFile\.SetCellFormat\(Integer, Integer, Integer, Integer, TFlxFormat, TFlxApplyFormat, Boolean\)
Changes part of the Cell format on a range of cells\. WARNING\! This method is slower than the other SetCellFormat versions, use it only if you do not care about maximum performance or if you just can't use the other SetCellFormat versions\.
This particular version of SetCellFormat has to read the format on each cell, modify it and write it back\.
While still very fast, it is not as fast as just setting the format on a cell\.


## Remarks

You can use this method for example to add a border on the top of a row of cells, keeping the existing font and pattern styles on the range\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetCellFormat(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const newFormat: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; const applyNewFormat: <a href="../../FlexCel.Core/TFlxApplyFormat/index.md">TFlxApplyFormat</a>; const exteriorBorders: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Row index of the top cell on the range \(1 based\)|
|const|**col1**|Integer|Column index of the left cell on the range \(1 based\)|
|const|**row2**|Integer|Row index of the bottom cell on the range \(1 based\)|
|const|**col2**|Integer|Column index of the right cell on the range \(1 based\)|
|const|**newFormat**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Format to apply to the cells\.|
|const|**applyNewFormat**|[TFlxApplyFormat](../../FlexCel.Core/TFlxApplyFormat/index.md)|Indicates which properties of newFormat will be applied to the cells\.|
|const|**exteriorBorders**|Boolean|When true, the format for the border will be applied only to the outer cells in the range\. This can be useful for example to draw a box around a range of cells, but not drawing borders inside the range\.<br />Other parameters, like the cell background, will still be applied to the full range\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


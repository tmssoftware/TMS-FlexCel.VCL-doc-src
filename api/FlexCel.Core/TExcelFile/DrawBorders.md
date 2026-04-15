---
uid: TExcelFile.DrawBorders
description: TExcelFile.DrawBorders
---

# TExcelFile\.DrawBorders Method

This method draws a border around a range of cells\.


## Remarks

This is just a shortcut for calling [SetCellFormat\(Integer, Integer, Integer, Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](SetCellFormat.md#texcelfilesetcellformatinteger-integer-integer-integer-tflxformat-tflxapplyformat-boolean)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DrawBorders(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const borderStyle: <a href="../TFlxBorderStyle.md">TFlxBorderStyle</a>; const borderColor: <a href="../TExcelColor/index.md">TExcelColor</a>; const exteriorBorders: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Row index of the top cell on the range \(1 based\)|
|const|**col1**|Integer|Column index of the left cell on the range \(1 based\)|
|const|**row2**|Integer|Row index of the bottom cell on the range \(1 based\)|
|const|**col2**|Integer|Column index of the right cell on the range \(1 based\)|
|const|**borderStyle**|[TFlxBorderStyle](../TFlxBorderStyle.md)|Style of the border to draw\.|
|const|**borderColor**|[TExcelColor](../TExcelColor/index.md)|Color of the border to draw\.|
|const|**exteriorBorders**|Boolean|When true, the format for the border will be applied only to the outer cells in the range\. This can be useful for example to draw a box around a range of cells, but not drawing borders inside the range\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)


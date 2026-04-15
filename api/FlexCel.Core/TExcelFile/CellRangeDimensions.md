---
uid: TExcelFile.CellRangeDimensions
description: TExcelFile.CellRangeDimensions
---

# TExcelFile\.CellRangeDimensions Method

Returns the height and width that would be used by a range of cells \(in Points, or 1/72 inches\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CellRangeDimensions(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const includeMargins: Boolean): <a href="../TUIRectangle/index.md">TUIRectangle</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**col1**|Integer|First column \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**row2**|Integer|Last row \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**col2**|Integer|Last column \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**includeMargins**|Boolean|If true, the dimensions reported will include all margins in the sheet\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


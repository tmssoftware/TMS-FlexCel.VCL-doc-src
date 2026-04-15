---
uid: TXlsFile.CellRangeDimensions
description: TXlsFile.CellRangeDimensions
---

# TXlsFile\.CellRangeDimensions Method

Returns the height and width that would be used by a range of cells \(in Points, or 1/72 inches\)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.CellRangeDimensions(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const includeMargins: Boolean): <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**col1**|Integer|First column \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**row2**|Integer|Last row \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**col2**|Integer|Last column \(1 based\)\. If you use a value less or equal than 0 here, this method will return the full sheet dimensions\.|
|const|**includeMargins**|Boolean|If true, the dimensions reported will include all margins in the sheet\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


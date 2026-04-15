---
uid: TXlsFile.GetHyperLinkCellRange
description: TXlsFile.GetHyperLinkCellRange
---

# TXlsFile\.GetHyperLinkCellRange Method

Returns the cell range a hyperlink refers to\.


## Remarks

While normally hyperlinks refer to a single cell, you can make them point to a range\. This method will return the first and last cell of the range that the hyperlink applies to\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetHyperLinkCellRange(const hyperLinkIndex: Integer): <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**hyperLinkIndex**|Integer|Index of the hyperlink \(1 based\)\.|


## Returns

Range the hyperlink applies to\.

## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TExcelFile.GetHyperLinkCellRange
description: TExcelFile.GetHyperLinkCellRange
---

# TExcelFile\.GetHyperLinkCellRange Method

Returns the cell range a hyperlink refers to\.


## Remarks

While normally hyperlinks refer to a single cell, you can make them point to a range\. This method will return the first and last cell of the range that the hyperlink applies to\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetHyperLinkCellRange(const hyperLinkIndex: Integer): <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**hyperLinkIndex**|Integer|Index of the hyperlink \(1 based\)\.|


## Returns

Range the hyperlink applies to\.

## See also

* [TExcelFile](../TExcelFile/index.md)


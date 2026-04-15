---
uid: TExcelFile.GetKeepColsTogether
description: TExcelFile.GetKeepColsTogether
---

# TExcelFile\.GetKeepColsTogether Method

Returns the value of level for a column as set in [KeepColsTogether](KeepColsTogether.md)\. Note that the last value of a "keep together" range is 0\.
For example, if you set KeepColsTogether\(1, 3, 8, true\); GetKeepColsTogether will return 8 for columns 1 and 2, and 0 for column 3\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetKeepColsTogether(const col: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index\. \(1 based\)|


## Returns

The Keep together level of the column\.

## See also

* [TExcelFile](../TExcelFile/index.md)


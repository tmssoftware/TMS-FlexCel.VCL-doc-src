---
uid: TXlsFile.GetKeepColsTogether
description: TXlsFile.GetKeepColsTogether
---

# TXlsFile\.GetKeepColsTogether Method

Returns the value of level for a column as set in [TExcelFile.KeepColsTogether](../../FlexCel.Core/TExcelFile/KeepColsTogether.md)\. Note that the last value of a "keep together" range is 0\.
For example, if you set KeepColsTogether\(1, 3, 8, true\); GetKeepColsTogether will return 8 for columns 1 and 2, and 0 for column 3\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetKeepColsTogether(const col: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index\. \(1 based\)|


## Returns

The Keep together level of the column\.

## See also

* [TXlsFile](../TXlsFile/index.md)


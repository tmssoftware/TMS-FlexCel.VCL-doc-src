---
uid: TXlsFile.GetKeepRowsTogether
description: TXlsFile.GetKeepRowsTogether
---

# TXlsFile\.GetKeepRowsTogether Method

Returns the value of level for a row as set in [TExcelFile.KeepRowsTogether](../../FlexCel.Core/TExcelFile/KeepRowsTogether.md)\. Note that the last value of a "keep together" range is 0\.
For example, if you set KeepRowsTogether\(1, 3, 8, true\); GetKeepRowsTogether will return 8 for rows 1 and 2, and 0 for row 3\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetKeepRowsTogether(const row: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index\. \(1 based\)|


## Returns

The Keep together level of the row\.

## See also

* [TXlsFile](../TXlsFile/index.md)


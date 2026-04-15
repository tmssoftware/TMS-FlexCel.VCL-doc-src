---
uid: TXlsFile.GetColCount
description: TXlsFile.GetColCount
---

# TXlsFile\.GetColCount Method

Number of columns actually used on a given sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColCount(const sheet: Integer; const includeFormattedColumns: Boolean): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet index where you want to find the columns \(1 based\)|
|const|**includeFormattedColumns**|Boolean|If true \(the default\) formatted columns \(for example a column you selected and painted yellow\) will be included in the count, even if it doesn't have data\.<br />|


## See also

* [TXlsFile](../TXlsFile/index.md)


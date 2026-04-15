---
uid: TXlsFile.HasVPageBreak
description: TXlsFile.HasVPageBreak
---

# TXlsFile\.HasVPageBreak Method

True if the sheet has a Manual Vertical page break on the column\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.HasVPageBreak(const col: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to check<br />Note that column can be 0, and this would mean a page break before column 1\. \(which Excel will ignore\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


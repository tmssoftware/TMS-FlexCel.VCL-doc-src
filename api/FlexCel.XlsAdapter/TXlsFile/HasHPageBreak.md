---
uid: TXlsFile.HasHPageBreak
description: TXlsFile.HasHPageBreak
---

# TXlsFile\.HasHPageBreak Method

True if the sheet has a Manual Horizontal page break on the row\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.HasHPageBreak(const row: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to check\.<br /><br />Note that row can be 0, and this would mean a page break before row 1\. \(which Excel will ignore\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


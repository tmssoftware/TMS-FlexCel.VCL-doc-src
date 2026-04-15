---
uid: TXlsFile.DeleteVPageBreak
description: TXlsFile.DeleteVPageBreak
---

# TXlsFile\.DeleteVPageBreak Method

Deletes all manual page breaks at col\. If there is no manual page break on col, this method will do nothing\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteVPageBreak(const col: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column where to delete the Page break\.<br /><br />Note that col can be 0, and this would mean a page break before column 1\. \(which Excel will ignore\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


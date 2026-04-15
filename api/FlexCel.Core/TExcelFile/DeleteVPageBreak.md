---
uid: TExcelFile.DeleteVPageBreak
description: TExcelFile.DeleteVPageBreak
---

# TExcelFile\.DeleteVPageBreak Method

Deletes all manual page breaks at col\. If there is no manual page break on col, this method will do nothing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteVPageBreak(const col: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column where to delete the Page break\.<br /><br />Note that col can be 0, and this would mean a page break before column 1\. \(which Excel will ignore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


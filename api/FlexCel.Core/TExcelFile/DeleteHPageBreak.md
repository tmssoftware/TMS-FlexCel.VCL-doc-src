---
uid: TExcelFile.DeleteHPageBreak
description: TExcelFile.DeleteHPageBreak
---

# TExcelFile\.DeleteHPageBreak Method

Deletes all manual page breaks at row\. If there is no manual page break on row, this method will do nothing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteHPageBreak(const row: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row where to delete the Page break\.<br /><br />Note that row can be 0, and this would mean a page break before row 1\. \(which Excel will ignore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


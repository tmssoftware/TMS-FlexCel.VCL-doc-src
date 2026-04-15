---
uid: TExcelFile.HasHPageBreak
description: TExcelFile.HasHPageBreak
---

# TExcelFile\.HasHPageBreak Method

True if the sheet has a Manual Horizontal page break on the row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.HasHPageBreak(const row: Integer): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to check\.<br /><br />Note that row can be 0, and this would mean a page break before row 1\. \(which Excel will ignore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.HasVPageBreak
description: TExcelFile.HasVPageBreak
---

# TExcelFile\.HasVPageBreak Method

True if the sheet has a Manual Vertical page break on the column\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.HasVPageBreak(const col: Integer): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to check<br />Note that column can be 0, and this would mean a page break before column 1\. \(which Excel will ignore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


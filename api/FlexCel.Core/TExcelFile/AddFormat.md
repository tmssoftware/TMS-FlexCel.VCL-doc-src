---
uid: TExcelFile.AddFormat
description: TExcelFile.AddFormat
---

# TExcelFile\.AddFormat Method

Adds a new format to the Excel format list\. If it already exists, it doesn't add a new one, so you can use this method for searching too\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddFormat(const format: <a href="../TFlxFormat/index.md">TFlxFormat</a>): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**format**|[TFlxFormat](../TFlxFormat/index.md)|Format to add to the list\.|


## Returns

Position on the list for the format\.

## See also

* [TExcelFile](../TExcelFile/index.md)


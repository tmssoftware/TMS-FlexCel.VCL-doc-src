---
uid: TXlsFile.AddFormat
description: TXlsFile.AddFormat
---

# TXlsFile\.AddFormat Method

Adds a new format to the Excel format list\. If it already exists, it doesn't add a new one, so you can use this method for searching too\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddFormat(const format: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**format**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Format to add to the list\.|


## Returns

Position on the list for the format\.

## See also

* [TXlsFile](../TXlsFile/index.md)


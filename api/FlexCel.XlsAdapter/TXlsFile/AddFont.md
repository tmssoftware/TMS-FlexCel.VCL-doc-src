---
uid: TXlsFile.AddFont
description: TXlsFile.AddFont
---

# TXlsFile\.AddFont Method

Adds a new font to the excel font list\.  If it already exists, it doesn't add a new one, so you can use this method for searching too\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddFont(const font: <a href="../../FlexCel.Core/TFlxFont/index.md">TFlxFont</a>): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**font**|[TFlxFont](../../FlexCel.Core/TFlxFont/index.md)|Font to add to the list\.|


## Returns

The position on the list for the added font\.

## See also

* [TXlsFile](../TXlsFile/index.md)


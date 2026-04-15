---
uid: TExcelFile.AddFont
description: TExcelFile.AddFont
---

# TExcelFile\.AddFont Method

Adds a new font to the excel font list\.  If it already exists, it doesn't add a new one, so you can use this method for searching too\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddFont(const font: <a href="../TFlxFont/index.md">TFlxFont</a>): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**font**|[TFlxFont](../TFlxFont/index.md)|Font to add to the list\.|


## Returns

The position on the list for the added font\.

## See also

* [TExcelFile](../TExcelFile/index.md)


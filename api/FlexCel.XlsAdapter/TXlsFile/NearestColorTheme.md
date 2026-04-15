---
uid: TXlsFile.NearestColorTheme
description: TXlsFile.NearestColorTheme
---

# TXlsFile\.NearestColorTheme Method

Returns the most similar entry on the theme palette for a given color\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.NearestColorTheme(const value: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; out tint: Double): <a href="../../FlexCel.Core/TThemeColor.md">TThemeColor</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color we want to use\.|
|out|**tint**|Double|Returns the tint to apply to the theme color\.|


## Returns

Most similar color on the theme palette\.

## See also

* [TXlsFile](../TXlsFile/index.md)


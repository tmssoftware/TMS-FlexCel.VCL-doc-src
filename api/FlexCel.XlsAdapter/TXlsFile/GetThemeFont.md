---
uid: TXlsFile.GetThemeFont
description: TXlsFile.GetThemeFont
---

# TXlsFile\.GetThemeFont Method

Gets the major of minor font scheme in the theme\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetThemeFont(const fontScheme: <a href="../../FlexCel.Core/TFontScheme.md">TFontScheme</a>): <a href="../../FlexCel.Core/TThemeFont/index.md">TThemeFont</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fontScheme**|[TFontScheme](../../FlexCel.Core/TFontScheme.md)|Font Scheme we want to get \(either minor or major\)\. Using "none" here will return null\.|


## Returns

Font definition\.

## See also

* [TXlsFile](../TXlsFile/index.md)


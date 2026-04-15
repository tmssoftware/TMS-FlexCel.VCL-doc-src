---
uid: TXlsFile.SetThemeFont
description: TXlsFile.SetThemeFont
---

# TXlsFile\.SetThemeFont Method

Sets either the minor or the major font for the theme\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetThemeFont(const fontScheme: <a href="../../FlexCel.Core/TFontScheme.md">TFontScheme</a>; const font: <a href="../../FlexCel.Core/TThemeFont/index.md">TThemeFont</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fontScheme**|[TFontScheme](../../FlexCel.Core/TFontScheme.md)|Font Scheme we want to set \(either minor or major\)\. Using "none" here will do nothing\.|
|const|**font**|[TThemeFont](../../FlexCel.Core/TThemeFont/index.md)|Font definition\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


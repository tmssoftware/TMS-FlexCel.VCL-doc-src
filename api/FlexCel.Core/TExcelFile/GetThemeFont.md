---
uid: TExcelFile.GetThemeFont
description: TExcelFile.GetThemeFont
---

# TExcelFile\.GetThemeFont Method

Gets the major of minor font scheme in the theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetThemeFont(const fontScheme: <a href="../TFontScheme.md">TFontScheme</a>): <a href="../TThemeFont/index.md">TThemeFont</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fontScheme**|[TFontScheme](../TFontScheme.md)|Font Scheme we want to get \(either minor or major\)\. Using "none" here will return null\.|


## Returns

Font definition\.

## See also

* [TExcelFile](../TExcelFile/index.md)


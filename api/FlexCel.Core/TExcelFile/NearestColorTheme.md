---
uid: TExcelFile.NearestColorTheme
description: TExcelFile.NearestColorTheme
---

# TExcelFile\.NearestColorTheme Method

Returns the most similar entry on the theme palette for a given color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.NearestColorTheme(const value: <a href="../TUIColor/index.md">TUIColor</a>; out tint: Double): <a href="../TThemeColor.md">TThemeColor</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TUIColor](../TUIColor/index.md)|Color we want to use\.|
|out|**tint**|Double|Returns the tint to apply to the theme color\.|


## Returns

Most similar color on the theme palette\.

## See also

* [TExcelFile](../TExcelFile/index.md)


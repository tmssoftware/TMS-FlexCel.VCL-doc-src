---
uid: TXlsFile.GetColorTheme
description: TXlsFile.GetColorTheme
---

# TXlsFile\.GetColorTheme Method

## Overloads

* [TXlsFile\.GetColorTheme\(TThemeColor\)](#txlsfilegetcolorthemetthemecolor)
* [TXlsFile\.GetColorTheme\(TPrimaryThemeColor\)](#txlsfilegetcolorthemetprimarythemecolor)

# TXlsFile\.GetColorTheme\(TThemeColor\)
Returns a color from the active theme palette, including semantic colors\.
Only has effect in Excel 2007\.

To get the full theme, look at [TExcelFile.GetTheme](../../FlexCel.Core/TExcelFile/GetTheme.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColorTheme(const themeColor: <a href="../../FlexCel.Core/TThemeColor.md">TThemeColor</a>): <a href="../../FlexCel.Core/TDrawingColor/index.md">TDrawingColor</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../../FlexCel.Core/TThemeColor.md)|Color of the theme to get\.|


## Returns

Color for the given theme\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetColorTheme\(TPrimaryThemeColor\)
Returns a color from the active theme palette, without including semantic colors\.
Only has effect in Excel 2007\.

To get the full theme, look at [TExcelFile.GetTheme](../../FlexCel.Core/TExcelFile/GetTheme.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColorTheme(const themeColor: <a href="../../FlexCel.Core/TPrimaryThemeColor.md">TPrimaryThemeColor</a>): <a href="../../FlexCel.Core/TDrawingColor/index.md">TDrawingColor</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TPrimaryThemeColor](../../FlexCel.Core/TPrimaryThemeColor.md)|Color of the theme to get\.|


## Returns

Color for the given theme\.

## See also

* [TXlsFile](../TXlsFile/index.md)


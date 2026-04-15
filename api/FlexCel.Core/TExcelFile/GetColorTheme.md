---
uid: TExcelFile.GetColorTheme
description: TExcelFile.GetColorTheme
---

# TExcelFile\.GetColorTheme Method

## Overloads

* [TExcelFile\.GetColorTheme\(TThemeColor\)](#texcelfilegetcolorthemetthemecolor)
* [TExcelFile\.GetColorTheme\(TPrimaryThemeColor\)](#texcelfilegetcolorthemetprimarythemecolor)

# TExcelFile\.GetColorTheme\(TThemeColor\)
Returns a color from the active theme palette, including semantic colors\.
Only has effect in Excel 2007\.

To get the full theme, look at [GetTheme](GetTheme.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColorTheme(const themeColor: <a href="../TThemeColor.md">TThemeColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../TThemeColor.md)|Color of the theme to get\.|


## Returns

Color for the given theme\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetColorTheme\(TPrimaryThemeColor\)
Returns a color from the active theme palette, without including semantic colors\.
Only has effect in Excel 2007\.

To get the full theme, look at [GetTheme](GetTheme.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetColorTheme(const themeColor: <a href="../TPrimaryThemeColor.md">TPrimaryThemeColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TPrimaryThemeColor](../TPrimaryThemeColor.md)|Color of the theme to get\.|


## Returns

Color for the given theme\.

## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.SetColorTheme
description: TExcelFile.SetColorTheme
---

# TExcelFile\.SetColorTheme Method

## Overloads

* [TExcelFile\.SetColorTheme\(TThemeColor, TDrawingColor\)](#texcelfilesetcolorthemetthemecolor-tdrawingcolor)
* [TExcelFile\.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](#texcelfilesetcolorthemetprimarythemecolor-tdrawingcolor)

# TExcelFile\.SetColorTheme\(TThemeColor, TDrawingColor\)
Changes a color on the Excel theme\. Only has effect in Excel 2007\.

**This method is provided to not break compatibility with older FlexCel versions\.
In newer code, you should use [SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](SetColorTheme.md#texcelfilesetcolorthemetprimarythemecolor-tdrawingcolor) instead\.**
If you want to change the full theme, use [GetTheme](GetTheme.md) and [SetTheme](SetTheme.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColorTheme(const themeColor: <a href="../TThemeColor.md">TThemeColor</a>; const value: <a href="../TDrawingColor/index.md">TDrawingColor</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../TThemeColor.md)|Color of the theme to change\. The only values that make sense are those included in [TPrimaryThemeColor](../TPrimaryThemeColor.md)\. Colors outside that range will be mapped to the nearest color: For example  Background1 will be mapped to Light1 and ForeGround1 will be mapped to Dark1\.|
|const|**value**|[TDrawingColor](../TDrawingColor/index.md)|Color to set\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)
Changes a color on the Excel theme\. Only has effect in Excel 2007\.

If you want to change the full theme, use [GetTheme](GetTheme.md) and [SetTheme](SetTheme.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColorTheme(const themeColor: <a href="../TPrimaryThemeColor.md">TPrimaryThemeColor</a>; const value: <a href="../TDrawingColor/index.md">TDrawingColor</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TPrimaryThemeColor](../TPrimaryThemeColor.md)|Color of the theme to change\.|
|const|**value**|[TDrawingColor](../TDrawingColor/index.md)|Color to set\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


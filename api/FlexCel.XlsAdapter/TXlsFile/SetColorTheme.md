---
uid: TXlsFile.SetColorTheme
description: TXlsFile.SetColorTheme
---

# TXlsFile\.SetColorTheme Method

## Overloads

* [TXlsFile\.SetColorTheme\(TThemeColor, TDrawingColor\)](#txlsfilesetcolorthemetthemecolor-tdrawingcolor)
* [TXlsFile\.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](#txlsfilesetcolorthemetprimarythemecolor-tdrawingcolor)

# TXlsFile\.SetColorTheme\(TThemeColor, TDrawingColor\)
Changes a color on the Excel theme\. Only has effect in Excel 2007\.

**This method is provided to not break compatibility with older FlexCel versions\.
In newer code, you should use [TExcelFile.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](../../FlexCel.Core/TExcelFile/SetColorTheme.md#texcelfilesetcolorthemetprimarythemecolor-tdrawingcolor) instead\.**
If you want to change the full theme, use [TExcelFile.GetTheme](../../FlexCel.Core/TExcelFile/GetTheme.md) and [TExcelFile.SetTheme](../../FlexCel.Core/TExcelFile/SetTheme.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColorTheme(const themeColor: <a href="../../FlexCel.Core/TThemeColor.md">TThemeColor</a>; const value: <a href="../../FlexCel.Core/TDrawingColor/index.md">TDrawingColor</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../../FlexCel.Core/TThemeColor.md)|Color of the theme to change\. The only values that make sense are those included in [TPrimaryThemeColor](../../FlexCel.Core/TPrimaryThemeColor.md)\. Colors outside that range will be mapped to the nearest color: For example  Background1 will be mapped to Light1 and ForeGround1 will be mapped to Dark1\.|
|const|**value**|[TDrawingColor](../../FlexCel.Core/TDrawingColor/index.md)|Color to set\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)
Changes a color on the Excel theme\. Only has effect in Excel 2007\.

If you want to change the full theme, use [TExcelFile.GetTheme](../../FlexCel.Core/TExcelFile/GetTheme.md) and [TExcelFile.SetTheme](../../FlexCel.Core/TExcelFile/SetTheme.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColorTheme(const themeColor: <a href="../../FlexCel.Core/TPrimaryThemeColor.md">TPrimaryThemeColor</a>; const value: <a href="../../FlexCel.Core/TDrawingColor/index.md">TDrawingColor</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TPrimaryThemeColor](../../FlexCel.Core/TPrimaryThemeColor.md)|Color of the theme to change\.|
|const|**value**|[TDrawingColor](../../FlexCel.Core/TDrawingColor/index.md)|Color to set\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


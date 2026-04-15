---
uid: TExcelColor.FromTheme
description: TExcelColor.FromTheme
---

# TExcelColor\.FromTheme Method

## Overloads

* [TExcelColor\.FromTheme\(TThemeColor\)](#texcelcolorfromthemetthemecolor)
* [TExcelColor\.FromTheme\(TThemeColor, Double\)](#texcelcolorfromthemetthemecolor-double)

# TExcelColor\.FromTheme\(TThemeColor\)
Returns a color class with a specified theme color and tint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromTheme(const themeColor: <a href="../TThemeColor.md">TThemeColor</a>): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../TThemeColor.md)|Theme color index\.|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.FromTheme\(TThemeColor, Double\)
Returns a color class with a specified theme color and tint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromTheme(const themeColor: <a href="../TThemeColor.md">TThemeColor</a>; const tint: Double): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**themeColor**|[TThemeColor](../TThemeColor.md)|Theme color index\.|
|const|**tint**|Double|Tint for the color\.<br /><br /><br /><br /><br />If you try to set a value less than \-1 it will be stored as \-1, and values bigger than 1 as 1\. No exceptions will be raised\.<br />|


## See also

* [TExcelColor](../TExcelColor/index.md)


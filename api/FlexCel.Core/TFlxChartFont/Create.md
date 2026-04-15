---
uid: TFlxChartFont.Create
description: TFlxChartFont.Create
---

# TFlxChartFont\.Create Method

## Overloads

* [TFlxChartFont\.Create](#tflxchartfontcreate)
* [TFlxChartFont\.Create\(TFlxFont\)](#tflxchartfontcreatetflxfont)
* [TFlxChartFont\.Create\(string, Integer\)](#tflxchartfontcreatestring-integer)
* [TFlxChartFont\.Create\(string, Integer, Boolean\)](#tflxchartfontcreatestring-integer-boolean)
* [TFlxChartFont\.Create\(string, Integer, TExcelColor, TFlxFontStyleSet, TFlxUnderline, TFontScheme\)](#tflxchartfontcreatestring-integer-texcelcolor-tflxfontstyleset-tflxunderline-tfontscheme)

# TFlxChartFont\.Create
Constructs a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxChartFont/index.md">TFlxChartFont</a>.Create: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; static; overload;</code></pre>

## See also

* [TFlxChartFont](../TFlxChartFont/index.md)

# TFlxChartFont\.Create\(TFlxFont\)
Constructs a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxChartFont/index.md">TFlxChartFont</a>.Create(const aFont: <a href="../TFlxFont/index.md">TFlxFont</a>): <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aFont**|[TFlxFont](../TFlxFont/index.md)|Font\.|


## See also

* [TFlxChartFont](../TFlxChartFont/index.md)

# TFlxChartFont\.Create\(string, Integer\)
Constructs a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxChartFont/index.md">TFlxChartFont</a>.Create(const aName: string; const Size20: Integer): <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the font\.|
|const|**Size20**|Integer|Height of the font \(in units of 1/20th of a point\)\. A Size20 = 200 means 10 points\.|


## See also

* [TFlxChartFont](../TFlxChartFont/index.md)

# TFlxChartFont\.Create\(string, Integer, Boolean\)
Constructs a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxChartFont/index.md">TFlxChartFont</a>.Create(const aName: string; const Size20: Integer; const aIsCalculated: Boolean): <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the font\.|
|const|**Size20**|Integer|Height of the font \(in units of 1/20th of a point\)\. A Size20 = 200 means 10 points\.|
|const|**aIsCalculated**|Boolean|If true, this font was calculated from defaults, and didn't had a real value in the file\.|


## See also

* [TFlxChartFont](../TFlxChartFont/index.md)

# TFlxChartFont\.Create\(string, Integer, TExcelColor, TFlxFontStyleSet, TFlxUnderline, TFontScheme\)
Constructs a new instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxChartFont/index.md">TFlxChartFont</a>.Create(const aName: string; const Size20: Integer; const aColor: <a href="../TExcelColor/index.md">TExcelColor</a>; const aStyle: <a href="../TFlxFontStyles.md">Set of TFlxFontStyles</a>; const aUnderline: <a href="../TFlxUnderline.md">TFlxUnderline</a>; const aScheme: <a href="../TFontScheme.md">TFontScheme</a>): <a href="../TFlxChartFont/index.md">TFlxChartFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string||
|const|**Size20**|Integer||
|const|**aColor**|[TExcelColor](../TExcelColor/index.md)||
|const|**aStyle**|[Set of TFlxFontStyles](../TFlxFontStyles.md)||
|const|**aUnderline**|[TFlxUnderline](../TFlxUnderline.md)||
|const|**aScheme**|[TFontScheme](../TFontScheme.md)||


## See also

* [TFlxChartFont](../TFlxChartFont/index.md)


---
uid: TChartRelativeRectangle.CalcRect
description: TChartRelativeRectangle.CalcRect
---

# TChartRelativeRectangle\.CalcRect Method

## Overloads

* [TChartRelativeRectangle\.CalcRect\(TUIPointF, TUIRectangle\)](#tchartrelativerectanglecalcrecttuipointf-tuirectangle)
* [TChartRelativeRectangle\.CalcRect\(TUIPointF, TUIRectangle, Double, Double\)](#tchartrelativerectanglecalcrecttuipointf-tuirectangle-double-double)

# TChartRelativeRectangle\.CalcRect\(TUIPointF, TUIRectangle\)
Calculates the dimension of the rectangle given the parent rectangle\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TChartRelativeRectangle/index.md">TChartRelativeRectangle</a>.CalcRect(const Point: <a href="../TUIPointF/index.md">TUIPointF</a>; const Coords: <a href="../TUIRectangle/index.md">TUIRectangle</a>): <a href="../TUIRectangle/index.md">TUIRectangle</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Point**|[TUIPointF](../TUIPointF/index.md)|Point with the default position to be used by the parent\. When mode is not factor, it is not used\.|
|const|**Coords**|[TUIRectangle](../TUIRectangle/index.md)|Parent rectangle coordinates\.|


## See also

* [TChartRelativeRectangle](../TChartRelativeRectangle/index.md)

# TChartRelativeRectangle\.CalcRect\(TUIPointF, TUIRectangle, Double, Double\)
Calculates the absolute rectangle given the parent rectangle\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TChartRelativeRectangle/index.md">TChartRelativeRectangle</a>.CalcRect(const Point: <a href="../TUIPointF/index.md">TUIPointF</a>; const Coords: <a href="../TUIRectangle/index.md">TUIRectangle</a>; const XDir: Double; const YDir: Double): <a href="../TUIRectangle/index.md">TUIRectangle</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Point**|[TUIPointF](../TUIPointF/index.md)|Point with the default position to be used by the parent\. When mode is not factor, it is not used\.|
|const|**Coords**|[TUIRectangle](../TUIRectangle/index.md)|Parent rectangle coordinates\.|
|const|**XDir**|Double|Set it to \-1 to reverse the x direction, or to 1 to keep it normal\.|
|const|**YDir**|Double|Set it to \-1 to reverse the y direction, or to 1 to keep it normal\.|


## See also

* [TChartRelativeRectangle](../TChartRelativeRectangle/index.md)


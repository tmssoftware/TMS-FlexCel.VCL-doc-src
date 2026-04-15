---
uid: TDrawingRichString.FirstRun
description: TDrawingRichString.FirstRun
---

# TDrawingRichString\.FirstRun Method

Returns the first run of the text\. Note that an empty TDrawingRichText can have a run anyway, while a TRichString can't\.
If there is no first run, the returned value will have a a negative FirstChar\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.FirstRun(const xls: TCoreExcelFile; ShapeThemeFont: <a href="../IShapeFont/index.md">IShapeFont</a>; const DefFont: <a href="../TFlxChartFont/index.md">TFlxChartFont</a>): <a href="../TRTFRun/index.md">TRTFRun</a>;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile||
||**ShapeThemeFont**|[IShapeFont](../IShapeFont/index.md)||
|const|**DefFont**|[TFlxChartFont](../TFlxChartFont/index.md)||


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)


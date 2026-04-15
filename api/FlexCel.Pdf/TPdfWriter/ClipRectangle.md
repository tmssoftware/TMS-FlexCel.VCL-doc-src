---
uid: TPdfWriter.ClipRectangle
description: TPdfWriter.ClipRectangle
---

# TPdfWriter\.ClipRectangle Method

Intersect the clip region with a rectangle specified by a pair of coordinates, a width, and a height\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.ClipRectangle(const x1: Double; const y1: Double; const width: Double; const height: Double; const exclude: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x1**|Double||
|const|**y1**|Double||
|const|**width**|Double||
|const|**height**|Double||
|const|**exclude**|Boolean|When true, all region OUTSIDE the rectangle will be intersected with the current clipping region\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


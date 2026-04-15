---
uid: TPdfWriter.ClipBeziers
description: TPdfWriter.ClipBeziers
---

# TPdfWriter\.ClipBeziers Method

Intersects the clipping area with a bezier region\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.ClipBeziers(const aPoints: <a href="../../FlexCel.Core/TUIPointF/index.md">TArray&lt;TUIPointF></a>; const exclude: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPoints**|[TArray\<TUIPointF>](../../FlexCel.Core/TUIPointF/index.md)|Array of points for the curve\. See GDI\+ DrawBeziers function for more information\.|
|const|**exclude**|Boolean|When true, all region OUTSIDE the region will be intersected with the current clipping region\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


---
uid: TPdfWriter.DrawAndFillPolygon
description: TPdfWriter.DrawAndFillPolygon
---

# TPdfWriter\.DrawAndFillPolygon Method

Draws and/or fills a polygon\. The shape will be closed\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawAndFillPolygon(const aPen: <a href="../../FlexCel.Core/TUIPen/index.md">TUIPen</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const aPoints: <a href="../../FlexCel.Core/TUIPointF/index.md">TArray&lt;TUIPointF></a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPen**|[TUIPen](../../FlexCel.Core/TUIPen/index.md)|Pen for the outline\. If null, no outline will be drawn\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush for filling\. If null, the shape will not be filled\.|
|const|**aPoints**|[TArray\<TUIPointF>](../../FlexCel.Core/TUIPointF/index.md)|Array of points for the polygon\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


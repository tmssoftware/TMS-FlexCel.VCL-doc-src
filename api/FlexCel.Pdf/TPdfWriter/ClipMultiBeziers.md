---
uid: TPdfWriter.ClipMultiBeziers
description: TPdfWriter.ClipMultiBeziers
---

# TPdfWriter\.ClipMultiBeziers Method

Intersects the clipping area with multiple bezier regions\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.ClipMultiBeziers(const exclude: Boolean; const aPoints: );</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**exclude**|Boolean|When true, all region OUTSIDE the region will be intersected with the current clipping region\.|
|const|**aPoints**||Array of points for the curve\. See GDI\+ DrawBeziers function for more information\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


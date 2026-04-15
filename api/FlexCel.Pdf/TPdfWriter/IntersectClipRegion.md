---
uid: TPdfWriter.IntersectClipRegion
description: TPdfWriter.IntersectClipRegion
---

# TPdfWriter\.IntersectClipRegion Method

Intersects the current clipping region with the new one\.
There is no command to reset or expand a clipping region, you need to use [SaveState](SaveState.md) and [RestoreState](RestoreState.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.IntersectClipRegion(const Rect: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Rect**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)||


## See also

* [TPdfWriter](../TPdfWriter/index.md)


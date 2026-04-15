---
uid: TPdfWriter.DrawAndFillMultiBeziers
description: TPdfWriter.DrawAndFillMultiBeziers
---

# TPdfWriter\.DrawAndFillMultiBeziers Method

Draws and/or fills a bezier path\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.DrawAndFillMultiBeziers(const aPen: <a href="../../FlexCel.Core/TUIPen/index.md">TUIPen</a>; const aBrush: <a href="../../FlexCel.Core/TUIBrush/index.md">TUIBrush</a>; const aPoints: TArray&lt;IUIPointFArray>; const aClosePath: TArray&lt;Boolean>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPen**|[TUIPen](../../FlexCel.Core/TUIPen/index.md)|Pen for the outline\. If null, no outline will be drawn\.|
|const|**aBrush**|[TUIBrush](../../FlexCel.Core/TUIBrush/index.md)|Brush for filling\. If null, the shape will not be filled\.|
|const|**aPoints**|TArray\<IUIPointFArray>|Array of array of points for the curves\. See GDI\+ DrawBeziers function for more information\.|
|const|**aClosePath**|TArray\<Boolean>|If true, the path will be closed\. Note that a closed path is different from an open path with same start and end points, because the closed path won't have linecaps at the end\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


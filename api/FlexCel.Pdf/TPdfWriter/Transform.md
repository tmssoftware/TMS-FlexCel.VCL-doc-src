---
uid: TPdfWriter.Transform
description: TPdfWriter.Transform
---

# TPdfWriter\.Transform Method

## Overloads

* [TPdfWriter\.Transform\(TUIPointF\)](#tpdfwritertransformtuipointf)
* [TPdfWriter\.Transform\(TUIPointF, TArray\<Double>\)](#tpdfwritertransformtuipointf-tarraydouble)

# TPdfWriter\.Transform\(TUIPointF\)
Transforms the point according to the current transformation Matrix\. See [GetMatrix](GetMatrix.md) to get the actual matrix\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfWriter/index.md">TPdfWriter</a>.Transform(const p: <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>): <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**p**|[TUIPointF](../../FlexCel.Core/TUIPointF/index.md)|Point you want to map to the user coordinates\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.Transform\(TUIPointF, TArray\<Double>\)
Transforms the point according to the given transformation Matrix\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfWriter/index.md">TPdfWriter</a>.Transform(const p: <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; const aDrawingMatrix: TArray&lt;Double&gt;): <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**p**|[TUIPointF](../../FlexCel.Core/TUIPointF/index.md)|Point you want to map to the user coordinates\.|
|const|**aDrawingMatrix**|TArray\<Double>|Matrix to use\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


---
uid: TPdfWriter.ScaleBy
description: TPdfWriter.ScaleBy
---

# TPdfWriter\.ScaleBy Method

## Overloads

* [TPdfWriter\.ScaleBy\(Double, Double\)](#tpdfwriterscalebydouble-double)
* [TPdfWriter\.ScaleBy\(Double, Double, Double, Double\)](#tpdfwriterscalebydouble-double-double-double)

# TPdfWriter\.ScaleBy\(Double, Double\)
Scales the canvas\. It premultiplies the matrix, to keep the correct order\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.ScaleBy(const xScale: Double; const yScale: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xScale**|Double|X Scale|
|const|**yScale**|Double|Y Scale|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.ScaleBy\(Double, Double, Double, Double\)
Scales the canvas around a point\. This is necessary when using negative scales to flip the image\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.ScaleBy(const x: Double; const y: Double; const xScale: Double; const yScale: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x**|Double|Point where the canvas is scaled\.|
|const|**y**|Double|Point where the canvas is scaled\.|
|const|**xScale**|Double|X Scale|
|const|**yScale**|Double|Y Scale|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


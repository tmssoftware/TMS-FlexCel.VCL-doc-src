---
uid: TPaperDimensions.Create
description: TPaperDimensions.Create
---

# TPaperDimensions\.Create Method

## Overloads

* [TPaperDimensions\.Create\(TPaperSize\)](#tpaperdimensionscreatetpapersize)
* [TPaperDimensions\.Create\(string, Double, Double\)](#tpaperdimensionscreatestring-double-double)

# TPaperDimensions\.Create\(TPaperSize\)
Creates a new TPaperDimensions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPaperDimensions/index.md">TPaperDimensions</a>.Create(const PaperSize: <a href="../TPaperSize.md">TPaperSize</a>): <a href="../TPaperDimensions/index.md">TPaperDimensions</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PaperSize**|[TPaperSize](../TPaperSize.md)|Excel standard papersize\.|


## See also

* [TPaperDimensions](../TPaperDimensions/index.md)

# TPaperDimensions\.Create\(string, Double, Double\)
Creates a new TPaperDimensions instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPaperDimensions/index.md">TPaperDimensions</a>.Create(const aPaperName: string; const aWidth: Double; const aHeight: Double): <a href="../TPaperDimensions/index.md">TPaperDimensions</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPaperName**|string|A string identifying the paper name|
|const|**aWidth**|Double|Width in inches/100|
|const|**aHeight**|Double|Height in inches/100|


## See also

* [TPaperDimensions](../TPaperDimensions/index.md)


---
uid: TPdfDestination.Create
description: TPdfDestination.Create
---

# TPdfDestination\.Create Method

## Overloads

* [TPdfDestination\.Create\(Integer\)](#tpdfdestinationcreateinteger)
* [TPdfDestination\.Create\(Integer, TZoomOptions\)](#tpdfdestinationcreateinteger-tzoomoptions)
* [TPdfDestination\.Create\(Integer, Double, Double, Double\)](#tpdfdestinationcreateinteger-double-double-double)

# TPdfDestination\.Create\(Integer\)
Creates a new TPdfDestination instance\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfDestination/index.md">TPdfDestination</a>.Create(const aPageNumber: Integer): <a href="../TPdfDestination/index.md">TPdfDestination</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPageNumber**|Integer|Page where the destination points to\. \(1 based\)|


## See also

* [TPdfDestination](../TPdfDestination/index.md)

# TPdfDestination\.Create\(Integer, TZoomOptions\)
Creates a new TPdfDestination instance\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfDestination/index.md">TPdfDestination</a>.Create(const aPageNumber: Integer; const aZoomOptions: <a href="../TZoomOptions.md">TZoomOptions</a>): <a href="../TPdfDestination/index.md">TPdfDestination</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPageNumber**|Integer|Page where the destination points to\. \(1 based\)|
|const|**aZoomOptions**|[TZoomOptions](../TZoomOptions.md)|Zoom options for this destination\.|


## See also

* [TPdfDestination](../TPdfDestination/index.md)

# TPdfDestination\.Create\(Integer, Double, Double, Double\)
Creates a new TPdfDestination instance with ZoomOptions = Zoom and the needed parameters\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfDestination/index.md">TPdfDestination</a>.Create(const aPageNumber: Integer; const aX: Double; const aY: Double; const aZoom: Double): <a href="../TPdfDestination/index.md">TPdfDestination</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPageNumber**|Integer|Page where the destination points to\. \(1 based\)|
|const|**aX**|Double|X offset in points from the left\.|
|const|**aY**|Double|Y offset in points from the top\.|
|const|**aZoom**|Double|Zoom to display in the destination\.|


## See also

* [TPdfDestination](../TPdfDestination/index.md)


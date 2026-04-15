---
uid: TClientAnchor.CalcImageCoords
description: TClientAnchor.CalcImageCoords
---

# TClientAnchor\.CalcImageCoords Method

## Overloads

* [TClientAnchor\.CalcImageCoords\(Double, Double, IRowColSize\)](#tclientanchorcalcimagecoordsdouble-double-irowcolsize)
* [TClientAnchor\.CalcImageCoords\(Double, Double, Double, Double, IRowColSize\)](#tclientanchorcalcimagecoordsdouble-double-double-double-irowcolsize)

# TClientAnchor\.CalcImageCoords\(Double, Double, IRowColSize\)
Calculates the width and height of the image in resolution\-independent\-pixels \(1/96 of an inch\)\. MAKE SURE THE ACTIVESHEET IN WORKBOOK IS THE CORRECT ONE\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TClientAnchor/index.md">TClientAnchor</a>.CalcImageCoords(var height: Double; var width: Double; const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|var|**height**|Double|Will return the height of the object\.|
|var|**width**|Double|Will return the width of the object\.|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|Workbook used to know the column widths and row heights\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)

# TClientAnchor\.CalcImageCoords\(Double, Double, Double, Double, IRowColSize\)
Calculates the width and height of the image in resolution\-independent\-pixels \(1/96 of an inch\)\. MAKE SURE THE ACTIVESHEET IN WORKBOOK IS THE CORRECT ONE\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TClientAnchor/index.md">TClientAnchor</a>.CalcImageCoords(out top: Double; out left: Double; out height: Double; out width: Double; const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|out|**top**|Double|Will return the top position of the start of the object in resolution\-independent\-pixels \(1/96 of an inch\)\.|
|out|**left**|Double|Will return the left position of the start of the object in resolution\-independent\-pixels \(1/96 of an inch\)\.|
|out|**height**|Double|Will return the height of the object\.|
|out|**width**|Double|Will return the width of the object\.|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|Workbook used to know the column widths and row heights\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)


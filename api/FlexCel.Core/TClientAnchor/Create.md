---
uid: TClientAnchor.Create
description: TClientAnchor.Create
---

# TClientAnchor\.Create Method

## Overloads

* [TClientAnchor\.Create](#tclientanchorcreate)
* [TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)](#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-irowcolsize)
* [TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer)
* [TClientAnchor\.Create\(Boolean, TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](#tclientanchorcreateboolean-tflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer)
* [TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)](#tclientanchorcreatetflxanchortype-integer-integer-integer-integer-integer-integer-integer-integer-irowcolsize)

# TClientAnchor\.Create
Creates an Empty ClientAnchor\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.Create: <a href="../TClientAnchor/index.md">TClientAnchor</a>; static; overload;</code></pre>

## See also

* [TClientAnchor](../TClientAnchor/index.md)

# TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)
Creates a new image based on the image size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.Create(const aAnchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const aRow1: Integer; const aPixDy1: Integer; const aCol1: Integer; const aPixDx1: Integer; const height: Integer; const width: Integer; const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): <a href="../TClientAnchor/index.md">TClientAnchor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAnchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|How the image behaves when copying/inserting cells\.|
|const|**aRow1**|Integer|Row where to insert the image\.|
|const|**aPixDy1**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aRow1\.|
|const|**aCol1**|Integer|Column where to insert the image\.|
|const|**aPixDx1**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aCol1\.|
|const|**height**|Integer|Height in resolution\-independent\-pixels \(1/96 of an inch\)\.|
|const|**width**|Integer|Width in resolution\-independent\-pixels \(1/96 of an inch\)\.|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|ExcelFile with the workbook, used to calculate the cells\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)

# TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)
Creates a new ClientAnchor object, based on cell coords\. Does not take in count actual image size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.Create(const aAnchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const aRow1: Integer; const aDy1: Integer; const aCol1: Integer; const aDx1: Integer; const aRow2: Integer; const aDy2: Integer; const aCol2: Integer; const aDx2: Integer): <a href="../TClientAnchor/index.md">TClientAnchor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAnchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|How the image behaves when copying/inserting cells\.|
|const|**aRow1**|Integer|First Row of object\.|
|const|**aDy1**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol1**|Integer|First column of object|
|const|**aDx1**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|
|const|**aRow2**|Integer|Last row of object\.|
|const|**aDy2**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol2**|Integer|Last column of object\.|
|const|**aDx2**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)

# TClientAnchor\.Create\(Boolean, TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)
Creates a new ClientAnchor object, based on cell coordinates\. Ignores actual image size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.Create(const aChartCoords: Boolean; const aAnchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const aRow1: Integer; const aDy1: Integer; const aCol1: Integer; const aDx1: Integer; const aRow2: Integer; const aDy2: Integer; const aCol2: Integer; const aDx2: Integer): <a href="../TClientAnchor/index.md">TClientAnchor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aChartCoords**|Boolean|If true, the object is inside a chart and rows and columns range from 0 to 4000\.|
|const|**aAnchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|How the image behaves when copying/inserting cells\.|
|const|**aRow1**|Integer|First Row of object\.|
|const|**aDy1**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol1**|Integer|First column of object\.|
|const|**aDx1**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|
|const|**aRow2**|Integer|Last row of object\.|
|const|**aDy2**|Integer|Delta y of image on 1/255 of a cell\. 0 means totally at the top, 128 on half of the cell, 255 means at the top of next cell\.|
|const|**aCol2**|Integer|Last column of object\.|
|const|**aDx2**|Integer|Delta x of image, on 1/1024 of a cell\.  0 means totally at the left, 512 on half of the cell, 1024 means at the left of next cell\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)

# TClientAnchor\.Create\(TFlxAnchorType, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer, IRowColSize\)
Creates a new image based on the image size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TClientAnchor/index.md">TClientAnchor</a>.Create(const aAnchorType: <a href="../TFlxAnchorType.md">TFlxAnchorType</a>; const aRow1: Integer; const aPixDy1: Integer; const aCol1: Integer; const aPixDx1: Integer; const aRow2: Integer; const aPixDy2: Integer; const aCol2: Integer; const aPixDx2: Integer; const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): <a href="../TClientAnchor/index.md">TClientAnchor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAnchorType**|[TFlxAnchorType](../TFlxAnchorType.md)|How the image behaves when copying/inserting cells\.|
|const|**aRow1**|Integer|Row where to insert the image\.|
|const|**aPixDy1**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aRow1\.|
|const|**aCol1**|Integer|Column where to insert the image\.|
|const|**aPixDx1**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aCol1\.|
|const|**aRow2**|Integer|Row where to insert the image\.|
|const|**aPixDy2**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aRow1\.|
|const|**aCol2**|Integer|Column where to insert the image\.|
|const|**aPixDx2**|Integer|Delta in resolution\-independent\-pixels \(1/96 of an inch\) that the image is moved from aCol1\.|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|ExcelFile with the workbook, used to calculate the cells\.|


## See also

* [TClientAnchor](../TClientAnchor/index.md)


---
uid: IExcelChart.AddAutoShape
description: IExcelChart.AddAutoShape
---

# IExcelChart\.AddAutoShape Method

Adds an autoshape to an existing embedded chart\. Note that the coordinates for the shape are in chart coords, meaning that only row1, row2, col1 and col2 are used, and they represent the percentage in 1/4000 of the coordinate\.
So 0 means the top and left of the parent chart, and 4000 means the bottom and right of the parent chart\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IExcelChart/index.md">IExcelChart</a>.AddAutoShape(shapeOptions: <a href="../IShapeProperties/index.md">IShapeProperties</a>): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**shapeOptions**|[IShapeProperties](../IShapeProperties/index.md)||


## Returns

The object index of the new shape\.

## See also

* [IExcelChart](../IExcelChart/index.md)


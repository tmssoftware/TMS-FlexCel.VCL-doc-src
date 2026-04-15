---
uid: TXlsBaseChart.AddAutoShape
description: TXlsBaseChart.AddAutoShape
---

# TXlsBaseChart\.AddAutoShape Method

Adds an autoshape to an existing embedded chart\. Note that the coordinates for the shape are in chart coords, meaning that only row1, row2, col1 and col2 are used, and they represent the percentage in 1/4000 of the coordinate\.
So 0 means the top and left of the parent chart, and 4000 means the bottom and right of the parent chart\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.AddAutoShape(shapeOptions: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>): Integer;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**shapeOptions**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)||


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


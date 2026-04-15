---
uid: TExcelFile.AddAutoShape
description: TExcelFile.AddAutoShape
---

# TExcelFile\.AddAutoShape Method

Adds an autoshape to the sheet\. You can add shapes to a worksheet, or to a chart sheet\.
For an example on how to add a shape, please create a shape in Excel, then open the file with APIMate and look at the generated code\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddAutoShape(shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape we want to add\.|


## Returns

The object index of the new shape\.

## See also

* [TExcelFile](../TExcelFile/index.md)


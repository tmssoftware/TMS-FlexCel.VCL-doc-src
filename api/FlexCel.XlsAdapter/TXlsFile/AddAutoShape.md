---
uid: TXlsFile.AddAutoShape
description: TXlsFile.AddAutoShape
---

# TXlsFile\.AddAutoShape Method

Adds an autoshape to the sheet\. You can add shapes to a worksheet, or to a chart sheet\.
For an example on how to add a shape, please create a shape in Excel, then open the file with APIMate and look at the generated code\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddAutoShape(shapeProperties: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**shapeProperties**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|Properties of the shape we want to add\.|


## Returns

The object index of the new shape\.

## See also

* [TXlsFile](../TXlsFile/index.md)


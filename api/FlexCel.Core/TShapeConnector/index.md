---
uid: TShapeConnector
description: TShapeConnector
---

# TShapeConnector Record

Used to link two different shapes with a connector\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TShapeConnector = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new ShapeConnector\.<br />|


## Properties

|Name|Description|
|---|---|
|[ShapeId](ShapeId.md)|The ID of the shape where this shape is linked\. A negative value means the shape is not connected\.<br />|
|[AnchorPoint](AnchorPoint.md)|This integer defines the anchor point used to link the connection\. The meaning of this number varies depending in the shape, for example a rectangle can have 4 anchor points \(one in each side\), while a triangle might have 3\.<br />|



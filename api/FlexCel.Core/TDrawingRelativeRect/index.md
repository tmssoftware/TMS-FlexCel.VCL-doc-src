---
uid: TDrawingRelativeRect
description: TDrawingRelativeRect
---

# TDrawingRelativeRect Record

A rectangle with coordinates used in a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingRelativeRect = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tdrawingrelativerectcreate)<br />  [Create\(Double, Double, Double, Double\)](Create.md#tdrawingrelativerectcreatedouble-double-double-double)<br />|
|[Equals](Equals.md)|Returns true if both classes contain the same rectangle\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Left](Left.md)|Percentage of the left coordinate\. Might be negative\.<br />|
|[Top](Top.md)|Percentage of the top coordinate\. Might be negative\.<br />|
|[Right](Right.md)|Percentage of the right coordinate\. Might be negative\.<br />|
|[Bottom](Bottom.md)|Percentage of the bottom coordinate\. Might be negative\.<br />|
|[Height](Height.md)|Bottom \- Top|
|[Width](Width.md)|Right \- Left|



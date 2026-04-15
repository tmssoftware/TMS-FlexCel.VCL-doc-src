---
uid: TChildAnchor
description: TChildAnchor
---

# TChildAnchor Record

A class to hold the offsets relative to the parent on grouped shapes\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TChildAnchor = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Dx1](Dx1.md)|Offset from the left on the parent, on percent of the total width of the parent\.<br />|
|[Dy1](Dy1.md)|Offset from the top on the parent, on percent of the total height of the parent\.<br />|
|[Dx2](Dx2.md)|Right coordinate of the box, in percent of the total width of the parent\.<br />|
|[Dy2](Dy2.md)|Bottom coordinate of the box, in percent of the total height of the parent\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tchildanchorcreate)<br />  [Create\(Double, Double, Double, Double\)](Create.md#tchildanchorcreatedouble-double-double-double)<br />|
|[Null](Null.md)|Creates a new null instance\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the Anchor\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for the object\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|



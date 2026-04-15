---
uid: TUIRectangle
description: TUIRectangle
---

# TUIRectangle Record

A platform independent rectangle\. Coordinates are floating point numbers\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUIRectangle = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new UIRectangle with the specified starting point, height and width\.<br />|
|[FromLTRB](FromLTRB.md)|Creates a new rectangle with the specified coordinates\.<br />|
|[Inflate](Inflate.md)|**Overloaded<br />**  [Inflate\(Double, Double\)](Inflate.md#tuirectangleinflatedouble-double)<br />  [Inflate\(TUIRectangle, Double, Double\)](Inflate.md#tuirectangleinflatetuirectangle-double-double)<br />|
|[Offset](Offset.md)|Moves the rectangle by \(dx, dy\), keeping the with and height the same\.<br />|
|[Union](Union.md)|Returns a new rectangle which contains both of the source rectangles\.<br />|
|[MakePositive](MakePositive.md)|This method ensures both width adn height are positive\. If they are negative, X and Y are moved so the rectangle is the same but with positive dimensions\.<br />|
|[Contains](Contains.md)|Returns true if point is inside the rectangle\.<br />|
|[FullyInside](FullyInside.md)|Returns true if this rectangle is fully inside other\.<br />|
|[FullyOutside](FullyOutside.md)|Returns true if this rectangle is fully outside other\.<br />|
|[ToString](ToString.md)|Returns a string with the rectangle's data\.<br />|
|[Intersect](Intersect.md)|Returns a rectangle which is the intersection of this one and the new one\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Empty](Empty.md)|Returns a rectangle with X = 0, Y = 0, Width = 0 and Height = 0\.<br />|
|[Location](Location.md)|Returns a TPointF with the Left and Top coordinates of the rectangle\.<br />|
|[BottomRight](BottomRight.md)|Returns a TPointF with the Right and Bottom coordinates of the rectangle\.<br />|
|[X](X.md)|Left coordinate of the rectangle\.<br />|
|[Y](Y.md)|Top coordinate of the rectangle\.<br />|
|[Width](Width.md)|Width of the rectangle\.<br />|
|[Height](Height.md)|Height of the rectangle\.<br />|
|[Top](Top.md)|Top coordinate\. This is the same as [Y](Y.md), but it is readonly\. \(Y is read write\)\.<br />|
|[Left](Left.md)|Left coordinate\. This is the same as [X](X.md), but it is readonly\. \(X is read write\)\.<br />|
|[Right](Right.md)|Right coordinate\.<br />|
|[Bottom](Bottom.md)|Bottom coordinate\.<br />|



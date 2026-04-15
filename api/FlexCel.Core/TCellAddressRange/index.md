---
uid: TCellAddressRange
description: TCellAddressRange
---

# TCellAddressRange Record

A class with 2 TCellAddress objects marking the start and end of a cell range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCellAddressRange = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\. Addresses can't be null\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|HashCode for the object|
|[HasValidAddress](HasValidAddress.md)|Returns true if row1 and col1 are > 0, row2 and col2 >= col1 and row2 and col2 \<= MaxRow and MaxCol|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[TopLeft](TopLeft.md)|The cell at the top left position in the range\. It can't be null\.<br />|
|[BottomRight](BottomRight.md)|The cell at the bottom right position in the range\. It can't be null\.<br />|



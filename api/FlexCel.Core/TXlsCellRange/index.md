---
uid: TXlsCellRange
description: TXlsCellRange
---

# TXlsCellRange Record

An Excel Cell range, 1\-based\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXlsCellRange = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Bottom](Bottom.md)|Last row on range\.<br />|
|[HasValue](HasValue.md)|False if the record doesn't have a defined value\. When this field is false, the values of left, right, top and bottom don't matter\.<br />|
|[Left](Left.md)|First column on range\.<br />|
|[Right](Right.md)|Last column on range\.<br />|
|[Top](Top.md)|First row on range\.<br />|


## Methods

|Name|Description|
|---|---|
|[CalcTopCell](CalcTopCell.md)|Returns the minimum top and left coordinates for an array of ranges\. If for example you have C7 and D5, this method will return C5|
|[Contains](Contains.md)|Returns true if the cell is inside the range\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#txlscellrangecreate)<br />  [Create\(string\)](Create.md#txlscellrangecreatestring)<br />  [Create\(Integer, Integer, Integer, Integer\)](Create.md#txlscellrangecreateinteger-integer-integer-integer)<br />|
|[Dec](Dec.md)|Returns a COPY of the range decremented by one\.<br />|
|[Equals](Equals.md)|Returns true if both objects are equal\.<br />|
|[FullRange](FullRange.md)|Creates a range with all cells on the sheet \(65536 rows x 256 columns in Excel 97\-2003\)|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[HasCol](HasCol.md)|True if the specified column is in the range|
|[HasRow](HasRow.md)|True if the specified row is in the range|
|[Inc](Inc.md)|Returns a COPY of the range incremented by one\.<br />|
|[Intersects](Intersects.md)|Returns true if this range intersects with another\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\. This is the inverse of [HasValue](HasValue.md)|
|[Null](Null.md)|Creates an invalid Cell range with the IsNull field set\.<br />|
|[Offset](Offset.md)|Creates a new range with the start at newTopRow, newLeftCol\.<br />|
|[ToString](ToString.md)|A human\-readable representation of the range\.<br />|
|[Transpose](Transpose.md)|Returns the range transposed, rows by columns\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[CellRef](CellRef.md)|Gets or sets the string that defines the 2D\-range in A1 notation\.<br />|
|[ColCount](ColCount.md)|Number of columns on the range\.<br />|
|[IsOneCell](IsOneCell.md)|Returns true if the range has only one cell\.<br />|
|[RowCount](RowCount.md)|Number of rows on the range\.<br />|



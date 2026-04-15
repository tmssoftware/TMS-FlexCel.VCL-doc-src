---
uid: TCellAddress
description: TCellAddress
---

# TCellAddress Record

Small class that can convert between a string reference \("A1"\) into row and col integers \(1,1\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCellAddress = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[ReadSimpleCol](ReadSimpleCol.md)|An optimized method to read cell references in xlsx files\. It won't allow sheets\.<br />|
|[Empty](Empty.md)|Returns a Cell Address pointing to an invalid reference\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string\)](Create.md#tcelladdresscreatestring)<br />  [Create\(Integer, Integer\)](Create.md#tcelladdresscreateinteger-integer)<br />  [Create\(Integer, Integer, Boolean, Boolean\)](Create.md#tcelladdresscreateinteger-integer-boolean-boolean)<br />  [Create\(string, Integer, Integer, Boolean, Boolean\)](Create.md#tcelladdresscreatestring-integer-integer-boolean-boolean)<br />|
|[QuoteSheet](QuoteSheet.md)|Quotes a sheet name if it is needed\. For example, Sheet 1 should be quoted as 'Sheet 1'|
|[NameIsReserved](NameIsReserved.md)|Returns true if the string can be a cell reference, like A1 or LVM78, or "R", "C", "TRUE" or "FALSE"\.<br />If this method returns true, you can't name a sheet or a named range with name\.<br />|
|[EncodeColumn](EncodeColumn.md)|Returns "A" for column 1, "B"  for 2 and so on\.<br />|
|[DecodeColumn](DecodeColumn.md)|Returns 1 for column "A", 2 for "B" and so on\. If the string isn't a valid column name, this method will return \-1\.<br />You normally will just want to create TCellAddress to convert between  cell references \(var cell = new TCellAddress\(row, col\); DoSomething\(&#8203;cell\.&#8203;Cell&#8203;Ref\)&#8203;\.&#8203;<br />But this method could be used in specific cases where you want only the column string and not the full address\.<br />|
|[ToString](ToString.md)|Returns the cell reference\.<br />|
|[CellRefR1C1](CellRefR1C1.md)|Returns the cell reference in the objects in R1C1 notation\.<br />|
|[TrySetCellRef](TrySetCellRef.md)|**Overloaded<br />**  [TrySetCellRef\(string\)](TrySetCellRef.md#tcelladdresstrysetcellrefstring)<br />  [TrySetCellRef\(string, TReferenceStyle, Integer, Integer\)](TrySetCellRef.md#tcelladdresstrysetcellrefstring-treferencestyle-integer-integer)<br />|
|[TryParseSheet](TryParseSheet.md)|Parses a string like Sheet1\!A1 into a sheet component and the rest\. If the sheet is quoted \('sheet 1'\) it will be unquoted\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of this object\.<br />|
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
|[Sheet](Sheet.md)|Sheet name of the reference\.<br />|
|[Row](Row.md)|Row index for this reference \(1\-based\)\.<br />|
|[Col](Col.md)|Column index for this reference \(1\-based\)\.<br />|
|[RowAbsolute](RowAbsolute.md)|True if the row is an absolute reference \(as in A$5\)|
|[ColAbsolute](ColAbsolute.md)|True if the column is an absolute reference \(as in $A5\)|
|[CellRef](CellRef.md)|Cell address in Excel A1 notation\. \(For example "A5"\)\.<br />Absolute references \($A$5\) will work too\.<br />|



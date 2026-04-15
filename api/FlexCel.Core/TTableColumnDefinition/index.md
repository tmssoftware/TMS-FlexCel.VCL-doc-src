---
uid: TTableColumnDefinition
description: TTableColumnDefinition
---

# TTableColumnDefinition Record

Contains the definition for a column in an Excel table\. This is mostly useful if the table doesn't have headers; since when the table has headers, the columns are inferred from the cells where the header is\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTableColumnDefinition = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string, Integer\)](Create.md#ttablecolumndefinitioncreatestring-integer)<br />  [Create\(string, Integer, NullableTTableFormula, NullableTTableFormula, string, string, string, TTotalsRowFunction, string\)](Create.md#ttablecolumndefinitioncreatestring-integer-nullablettableformula-nullablettableformula-string-string-string-ttotalsrowfunction-string)<br />|
|[GetHashCode](GetHashCode.md)|Hashcode for the column\.<br />|
|[Equals](Equals.md)|Returns true if obj has the same data as this instance\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the column\. Note that when the table has a header row, the names will be  read from the cells where the column is, not from this name\. This property is mostly useful if the table doesn't have headers\.<br />|
|[Id](Id.md)|Unique id that identifies this column\. It should not change when the column name changes or the column moves its position\.<br />|
|[CalculatedColumn&#8203;Formula](CalculatedColumnFormula.md)|Stores the formula that is used to perform the calculation for each cell in this column\.<br />Note that the column can have different formulas from this one, but this is normally not the case\.<br />This formula is also used by Excel to automatically add new formulas when you add new rows to the table\. FlexCel doesn't automatically adds this formula to the new rows, you need to set the cells to the formula manually if you want to\.<br />|
|[TotalsRowFormula](TotalsRowFormula.md)|A custom formula for aggregating values from the column\. This formula is only used if [TotalsRowFunction](TotalsRowFunction.md) is set to "Custom"\. Additionally, FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.<br />If the table doesn't have a total row, then this value will be used\.<br />|
|[DataCellStyle](DataCellStyle.md)|Style for the cells in the column, if they don't have a given cell style\.<br />This property has more priority than the table cell style, but less than the cell style\.<br />This value is used when adding a new empty row as a default for the column\.<br />|
|[HeaderRowCellStyle](HeaderRowCellStyle.md)|Style for the header row cell in the column, if it doesn't have a given cell style\.<br />This property has more priority than the table header row cell style, but less than the cell style\.<br />FlexCel will ignore this value when adding a table and read the style from the cell itself\.<br />|
|[TotalsRowCellStyle](TotalsRowCellStyle.md)|Style for the totals row cell in the column, if it doesn't have a given cell style\.<br />This property has more priority than the table totals row cell style, but less than the cell style\.<br />FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.<br />If the table doesn't have a total row, then this value will be used\.<br />|
|[TotalsRowFunction](TotalsRowFunction.md)|An enumeration that specifies what function is used to aggregate the data in a column\.<br />When set to custom, the value in [TotalsRowFormula](TotalsRowFormula.md) is used instead\.<br />Additionally, FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.<br />If the table doesn't have a total row, then this value will be used\.<br />|
|[TotalsRowLabel](TotalsRowLabel.md)|A String to show in the totals row cell for this column\.<br />This is ignored unless [TotalsRowFunction](TotalsRowFunction.md) is none\.<br />Additionally, FlexCel will ignore this value when adding a table with totals and read the formula from the cell itself\.<br />If the table doesn't have a total row, then this value will be used\.<br />|



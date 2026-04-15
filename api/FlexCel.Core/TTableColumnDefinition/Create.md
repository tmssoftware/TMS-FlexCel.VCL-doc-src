---
uid: TTableColumnDefinition.Create
description: TTableColumnDefinition.Create
---

# TTableColumnDefinition\.Create Method

## Overloads

* [TTableColumnDefinition\.Create\(string, Integer\)](#ttablecolumndefinitioncreatestring-integer)
* [TTableColumnDefinition\.Create\(string, Integer, NullableTTableFormula, NullableTTableFormula, string, string, string, TTotalsRowFunction, string\)](#ttablecolumndefinitioncreatestring-integer-nullablettableformula-nullablettableformula-string-string-string-ttotalsrowfunction-string)

# TTableColumnDefinition\.Create\(string, Integer\)
Creates a new TTableColumnDefinition with a Name and Id\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.Create(const aName: string; const aId: Integer): <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the column\.|
|const|**aId**|Integer|Id used to identify the column\. It must be unique in the table, and it must not change when the column name change or the column moves\.|


## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)

# TTableColumnDefinition\.Create\(string, Integer, NullableTTableFormula, NullableTTableFormula, string, string, string, TTotalsRowFunction, string\)
Creates a new TTableColumnDefinition\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>.Create(const aName: string; const aId: Integer; const aCalculatedColumnFormula: NullableTTableFormula; const aTotalsRowFormula: NullableTTableFormula; const aDataCellStyle: string; const aHeaderRowCellStyle: string; const aTotalsRowCellStyle: string; const aTotalsRowFunction: <a href="../TTotalsRowFunction.md">TTotalsRowFunction</a>; const aTotalsRowLabel: string): <a href="../TTableColumnDefinition/index.md">TTableColumnDefinition</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aName**|string|Name of the column\.|
|const|**aId**|Integer|Id used to identify the column\. It must be unique in the table, and it must not change when the column name change or the column moves\.|
|const|**aCalculatedColumnFormula**|NullableTTableFormula|Stores the formula that is used to perform the calculation for each cell in this column\.<br />Note that the column can have different formulas from this one, but this is normally not the case\.<br />This formula is also used by Excel to automatically add new formulas when you add new rows to the table\. FlexCel doesn't automatically adds this formula to the new rows, you need to set the cells to the formula manually if you want to\.|
|const|**aTotalsRowFormula**|NullableTTableFormula|A custom formula for aggregating values from the column\. This formula is only used if [TotalsRowFunction](TotalsRowFunction.md) is set to "Custom"\.|
|const|**aDataCellStyle**|string|Style for the cells in the column, if they don't have a given cell style\.|
|const|**aHeaderRowCellStyle**|string|Style for the header row cell in the column, if it doesn't have a given cell style\.|
|const|**aTotalsRowCellStyle**|string|Style for the totals row cell in the column, if it doesn't have a given cell style\.|
|const|**aTotalsRowFunction**|[TTotalsRowFunction](../TTotalsRowFunction.md)|An enumeration that specifies what function is used to aggregate the data in a column\.|
|const|**aTotalsRowLabel**|string|A String to show in the totals row cell for this column\. This is ignored unless [TotalsRowFunction](TotalsRowFunction.md) is none\.|


## See also

* [TTableColumnDefinition](../TTableColumnDefinition/index.md)


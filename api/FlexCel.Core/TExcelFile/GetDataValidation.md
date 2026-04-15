---
uid: TExcelFile.GetDataValidation
description: TExcelFile.GetDataValidation
---

# TExcelFile\.GetDataValidation Method

## Overloads

* [TExcelFile\.GetDataValidation\(Integer, Integer\)](#texcelfilegetdatavalidationinteger-integer)
* [TExcelFile\.GetDataValidation\(Integer, Integer, TXlsCellRange\)](#texcelfilegetdatavalidationinteger-integer-txlscellrange)

# TExcelFile\.GetDataValidation\(Integer, Integer\)
Returns the validation information for a specific cell\. If the cell has no Data Validation associated, this method returns null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetDataValidation(const row: Integer; const col: Integer): <a href="../TDataValidationInfo/index.md">TDataValidationInfo</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|


## Returns

The data validation for a cell, or null if the cell has no Data Validation associated\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetDataValidation\(Integer, Integer, TXlsCellRange\)
Returns the validation information for a specific cell\. If the cell has no Data Validation associated, this method returns null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetDataValidation(const row: Integer; const col: Integer; out dvRange: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>): <a href="../TDataValidationInfo/index.md">TDataValidationInfo</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row of the cell \(1 based\)|
|const|**col**|Integer|Column of the cell \(1 based\)|
|out|**dvRange**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells where the data validation is applied\.|


## Returns

The data validation for a cell, or null if the cell has no Data Validation associated\.

## See also

* [TExcelFile](../TExcelFile/index.md)


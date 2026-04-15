---
uid: TExcelFile.GetDataValidationInfo
description: TExcelFile.GetDataValidationInfo
---

# TExcelFile\.GetDataValidationInfo Method

Returns the data validation information for an entry of the index\.
There are 2 ways you can access the data validation information on a sheet:
1. If you know the row and column where you want to look, you can use [GetDataValidation\(Integer, Integer\)](GetDataValidation.md#texcelfilegetdatavalidationinteger-integer) to return the data validation in the cell\.
2. If you want to find out all data validation structures in the sheet, you can use [DataValidationCount](DataValidationCount.md),  [GetDataValidationInfo](GetDataValidationInfo.md) and [GetDataValidationRanges](GetDataValidationRanges.md) to loop over all existing data validations\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetDataValidationInfo(const index: Integer): <a href="../TDataValidationInfo/index.md">TDataValidationInfo</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of data validations\. \(1 based\)|


## Returns

Data validation information\.

## See also

* [TExcelFile](../TExcelFile/index.md)


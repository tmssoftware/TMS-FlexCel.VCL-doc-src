---
uid: TXlsFile.GetDataValidationInfo
description: TXlsFile.GetDataValidationInfo
---

# TXlsFile\.GetDataValidationInfo Method

Returns the data validation information for an entry of the index\.
There are 2 ways you can access the data validation information on a sheet:
1. If you know the row and column where you want to look, you can use [TExcelFile.GetDataValidation\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetDataValidation.md#texcelfilegetdatavalidationinteger-integer) to return the data validation in the cell\.
2. If you want to find out all data validation structures in the sheet, you can use [TExcelFile.DataValidationCount](../../FlexCel.Core/TExcelFile/DataValidationCount.md),  [TExcelFile.GetDataValidationInfo](../../FlexCel.Core/TExcelFile/GetDataValidationInfo.md) and [TExcelFile.GetDataValidationRanges](../../FlexCel.Core/TExcelFile/GetDataValidationRanges.md) to loop over all existing data validations\.



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetDataValidationInfo(const index: Integer): <a href="../../FlexCel.Core/TDataValidationInfo/index.md">TDataValidationInfo</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of data validations\. \(1 based\)|


## Returns

Data validation information\.

## See also

* [TXlsFile](../TXlsFile/index.md)


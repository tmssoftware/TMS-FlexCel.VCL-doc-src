---
uid: TXlsFile.GetDataValidationRanges
description: TXlsFile.GetDataValidationRanges
---

# TXlsFile\.GetDataValidationRanges Method

Returns a list of ranges for which a data validation definition applies\.
There are 2 ways you can access the data validation information on a sheet:
1. If you know the row and column where you want to look, you can use [TExcelFile.GetDataValidation\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/GetDataValidation.md#texcelfilegetdatavalidationinteger-integer) to return the data validation in the cell\.
2. If you want to find out all data validation structures in the sheet, you can use [TExcelFile.DataValidationCount](../../FlexCel.Core/TExcelFile/DataValidationCount.md),  [TExcelFile.GetDataValidationInfo](../../FlexCel.Core/TExcelFile/GetDataValidationInfo.md) and [TExcelFile.GetDataValidationRanges](../../FlexCel.Core/TExcelFile/GetDataValidationRanges.md) to loop over all existing data validations\.



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetDataValidationRanges(const index: Integer): <a href="../../FlexCel.Core/TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of data validations\. \(1 based\)|


## Returns

A list of cell ranges\.

## See also

* [TXlsFile](../TXlsFile/index.md)


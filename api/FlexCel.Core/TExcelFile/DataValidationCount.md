---
uid: TExcelFile.DataValidationCount
description: TExcelFile.DataValidationCount
---

# TExcelFile.DataValidationCount Property

Returns the number of DataValidation structures in the active sheet\.
There are 2 ways you can access the data validation information on a sheet:
1. If you know the row and column where you want to look, you can use [GetDataValidation\(Integer, Integer\)](GetDataValidation.md#texcelfilegetdatavalidationinteger-integer) to return the data validation in the cell\.
2. If you want to find out all data validation structures in the sheet, you can use [DataValidationCount](DataValidationCount.md),  [GetDataValidationInfo](GetDataValidationInfo.md) and [GetDataValidationRanges](GetDataValidationRanges.md) to loop over all existing data validations\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.DataValidationCount: Integer</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


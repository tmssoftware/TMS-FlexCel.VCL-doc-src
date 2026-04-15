---
uid: TXlsFile.AutofitMarkedRowsAndCols
description: TXlsFile.AutofitMarkedRowsAndCols
---

# TXlsFile\.AutofitMarkedRowsAndCols Method

Autofits all the rows and columns on a sheet that have been previously marked with the [TExcelFile.MarkRowForAutofit\(Integer, Boolean, Double\)](../../FlexCel.Core/TExcelFile/MarkRowForAutofit.md#texcelfilemarkrowforautofitinteger-boolean-double)  and [TExcelFile.MarkColForAutofit\(Integer, Boolean, Double\)](../../FlexCel.Core/TExcelFile/MarkColForAutofit.md#texcelfilemarkcolforautofitinteger-boolean-double) methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AutofitMarkedRowsAndCols(const keepSizesAutomatic: Boolean; const ignoreStringsOnColumnFit: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const minWidth: Integer; const maxWidth: Integer; const autofitMerged: <a href="../../FlexCel.Core/TAutofitMerged.md">TAutofitMerged</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**keepSizesAutomatic**|Boolean|When true, no modifications will be done to the "autofit" status of the rows\. When false, all rows will be marked as "no autofit", so when you open this file in Excel it will not be resized by Excel, and the sizes when printing/export to PDF from Excel will be the same as FlexCel, even when some cells might appear "cut" when printing on Excel\.<br />|
|const|**ignoreStringsOnColumnFit**|Boolean|When true, cells containing strings will not be autofitted\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns and rows will be adjusted to 110%% percent of what their calculated width and height was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|
|const|**minWidth**|Integer|Minimum final width for the column to autofit\. If the calculated value is less than minWidth, column size will be set to minWidth\.<br /><br />A negative value on minWidth means the column size will be no smaller than the original width\.|
|const|**maxWidth**|Integer|Maximum final width for the column to autofit\. If the calculated value is more than maxWidth, column size will be set to maxWidth\.<br /><br />maxWidth = 0 means no maxWidth\.<br /><br />A negative value on maxWidth means the column size will be no bigger than the original width\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../../FlexCel.Core/TAutofitMerged.md)|Specifies which row in a merged cell using more than one row, or which column in a merged cell with more than one column will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last row or column in the merged range\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


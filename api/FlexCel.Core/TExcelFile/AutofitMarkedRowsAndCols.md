---
uid: TExcelFile.AutofitMarkedRowsAndCols
description: TExcelFile.AutofitMarkedRowsAndCols
---

# TExcelFile\.AutofitMarkedRowsAndCols Method

## Overloads

* [TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double\)](#texcelfileautofitmarkedrowsandcolsboolean-boolean-double)
* [TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double, Integer, Integer, Integer, Integer, Integer\)](#texcelfileautofitmarkedrowsandcolsboolean-boolean-double-integer-integer-integer-integer-integer)
* [TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double, Integer, Integer, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitmarkedrowsandcolsboolean-boolean-double-integer-integer-integer-integer-integer-tautofitmerged)

# TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double\)
Autofits all the rows and columns on a sheet that have been previously marked with the [MarkRowForAutofit\(Integer, Boolean, Double\)](MarkRowForAutofit.md#texcelfilemarkrowforautofitinteger-boolean-double)  and [MarkColForAutofit\(Integer, Boolean, Double\)](MarkColForAutofit.md#texcelfilemarkcolforautofitinteger-boolean-double) methods\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitMarkedRowsAndCols(const keepSizesAutomatic: Boolean; const ignoreStringsOnColumnFit: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**keepSizesAutomatic**|Boolean|When true, no modifications will be done to the "autofit" status of the rows\. When false, all rows will be marked as "no autofit", so when you open this file in Excel it will not be resized by Excel, and the sizes when printing/export to PDF from Excel will be the same as FlexCel, even when some cells might appear "cut" when printing on Excel\.<br />|
|const|**ignoreStringsOnColumnFit**|Boolean|When true, cells containing strings will not be autofitted\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns and rows will be adjusted to 110%% percent of what their calculated width and height was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double, Integer, Integer, Integer, Integer, Integer\)
Autofits all the rows and columns on a sheet that have been previously marked with the [MarkRowForAutofit\(Integer, Boolean, Double\)](MarkRowForAutofit.md#texcelfilemarkrowforautofitinteger-boolean-double)  and [MarkColForAutofit\(Integer, Boolean, Double\)](MarkColForAutofit.md#texcelfilemarkcolforautofitinteger-boolean-double) methods\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitMarkedRowsAndCols(const keepSizesAutomatic: Boolean; const ignoreStringsOnColumnFit: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const minWidth: Integer; const maxWidth: Integer); overload;</code></pre>

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


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double, Integer, Integer, Integer, Integer, Integer, TAutofitMerged\)
Autofits all the rows and columns on a sheet that have been previously marked with the [MarkRowForAutofit\(Integer, Boolean, Double\)](MarkRowForAutofit.md#texcelfilemarkrowforautofitinteger-boolean-double)  and [MarkColForAutofit\(Integer, Boolean, Double\)](MarkColForAutofit.md#texcelfilemarkcolforautofitinteger-boolean-double) methods\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitMarkedRowsAndCols(const keepSizesAutomatic: Boolean; const ignoreStringsOnColumnFit: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const minWidth: Integer; const maxWidth: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload; virtual; abstract;</code></pre>

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
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which row in a merged cell using more than one row, or which column in a merged cell with more than one column will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last row or column in the merged range\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


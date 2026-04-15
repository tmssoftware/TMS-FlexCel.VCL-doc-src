---
uid: TExcelFile.AutofitRowsOnWorkbook
description: TExcelFile.AutofitRowsOnWorkbook
---

# TExcelFile\.AutofitRowsOnWorkbook Method

## Overloads

* [TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double\)](#texcelfileautofitrowsonworkbookboolean-boolean-double)
* [TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double, Integer, Integer, Integer\)](#texcelfileautofitrowsonworkbookboolean-boolean-double-integer-integer-integer)
* [TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitrowsonworkbookboolean-boolean-double-integer-integer-integer-tautofitmerged)

# TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double\)
Autofits all the rows on all sheets on a workbook that are set to autofit so they adapt their height to show all the text inside\.
Note that due to GDI\+ / GDI incompatibilities, the heights calculated by FlexCel will not be exactly the same than the ones calculated by Excel\. So when you open this workbook in Excel, Excel might re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepSizesAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRowsOnWorkbook(const autofitNotAutofittingRows: Boolean; const keepSizesAutomatic: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepSizesAutomatic**|Boolean|When true, no modifications will be done to the "autofit" status of the rows\. When false, all rows will be marked as "no autofit", so when you open this file in Excel it will not be resized by Excel, and the printing/export to PDF from Excel will be the same as FlexCel\.<br />|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double, Integer, Integer, Integer\)
Autofits all the rows on all sheets on a workbook that are set to autofit so they adapt their height to show all the text inside\.
Note that due to GDI\+ / GDI incompatibilities, the heights calculated by FlexCel will not be exactly the same than the ones calculated by Excel\. So when you open this workbook in Excel, Excel might re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepSizesAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRowsOnWorkbook(const autofitNotAutofittingRows: Boolean; const keepSizesAutomatic: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepSizesAutomatic**|Boolean|When true, no modifications will be done to the "autofit" status of the rows\. When false, all rows will be marked as "no autofit", so when you open this file in Excel it will not be resized by Excel, and the printing/export to PDF from Excel will be the same as FlexCel\.<br />|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRowsOnWorkbook\(Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)
Autofits all the rows on all sheets on a workbook that are set to autofit so they adapt their height to show all the text inside\.
Note that due to GDI\+ / GDI incompatibilities, the heights calculated by FlexCel will not be exactly the same than the ones calculated by Excel\. So when you open this workbook in Excel, Excel might re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepSizesAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRowsOnWorkbook(const autofitNotAutofittingRows: Boolean; const keepSizesAutomatic: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepSizesAutomatic**|Boolean|When true, no modifications will be done to the "autofit" status of the rows\. When false, all rows will be marked as "no autofit", so when you open this file in Excel it will not be resized by Excel, and the printing/export to PDF from Excel will be the same as FlexCel\.<br />|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which row in a merged cell using more than one row will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last row\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


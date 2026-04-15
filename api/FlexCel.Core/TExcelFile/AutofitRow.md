---
uid: TExcelFile.AutofitRow
description: TExcelFile.AutofitRow
---

# TExcelFile\.AutofitRow Method

## Overloads

* [TExcelFile\.AutofitRow\(Integer, Boolean, Double\)](#texcelfileautofitrowinteger-boolean-double)
* [TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double\)](#texcelfileautofitrowinteger-integer-boolean-boolean-double)
* [TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer\)](#texcelfileautofitrowinteger-integer-boolean-boolean-double-integer-integer-integer)
* [TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitrowinteger-integer-boolean-boolean-double-integer-integer-integer-tautofitmerged)
* [TExcelFile\.AutofitRow\(Integer, Integer, Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitrowinteger-integer-integer-integer-boolean-boolean-double-integer-integer-integer-tautofitmerged)

# TExcelFile\.AutofitRow\(Integer, Boolean, Double\)
Autofits a row so it adapts its height to show all the text inside\. It does not matter if the row is set to Autofit or not in Excel\.
Note that due to GDI\+ / GDI incompatibilities, the height calculated by FlexCel will not be exactly the same than the one calculated by Excel\. So when you open this workbook in Excel, Excel will re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepHeightAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRow(const row: Integer; const keepHeightAutomatic: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row to Autofit\.|
|const|**keepHeightAutomatic**|Boolean|If true, rows will be still autoheight when you open the file in Excel, so Excel will recalculate the values, probably changing the page breaks\. If you set it to false, rows will be fixed in size, and when you open it on Excel they will remain so\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double\)
Autofits a range of rows so they adapt their height to show all the text inside\. Note that due to GDI\+ / GDI incompatibilities, the height calculated by FlexCel will not be exactly the same than the one calculated by Excel\. So when you open this workbook in Excel, Excel will re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepHeightAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRow(const row1: Integer; const row2: Integer; const autofitNotAutofittingRows: Boolean; const keepHeightAutomatic: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row to autofit\.|
|const|**row2**|Integer|Last row to autofit\.|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepHeightAutomatic**|Boolean|If true, rows will be still autoheight when you open the file in Excel, so Excel will recalculate the values, probably changing the page breaks\. If you set it to false, rows will be fixed in size, and when you open it on Excel they will remain so\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer\)
Autofits a range of rows so they adapt their height to show all the text inside\. Note that due to GDI\+ / GDI incompatibilities, the height calculated by FlexCel will not be exactly the same than the one calculated by Excel\. So when you open this workbook in Excel, Excel will re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepHeightAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRow(const row1: Integer; const row2: Integer; const autofitNotAutofittingRows: Boolean; const keepHeightAutomatic: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row to autofit\.|
|const|**row2**|Integer|Last row to autofit\.|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepHeightAutomatic**|Boolean|If true, rows will be still autoheight when you open the file in Excel, so Excel will recalculate the values, probably changing the page breaks\. If you set it to false, rows will be fixed in size, and when you open it on Excel they will remain so\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofitting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRow\(Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)
Autofits a range of rows so they adapt their height to show all the text inside\. Note that due to GDI\+ / GDI incompatibilities, the height calculated by FlexCel will not be exactly the same than the one calculated by Excel\. So when you open this workbook in Excel, Excel will re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepHeightAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRow(const row1: Integer; const row2: Integer; const autofitNotAutofittingRows: Boolean; const keepHeightAutomatic: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row to autofit\.|
|const|**row2**|Integer|Last row to autofit\.|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepHeightAutomatic**|Boolean|If true, rows will be still autoheight when you open the file in Excel, so Excel will recalculate the values, probably changing the page breaks\. If you set it to false, rows will be fixed in size, and when you open it on Excel they will remain so\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which row in a merged cell using more than one row will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last row\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitRow\(Integer, Integer, Integer, Integer, Boolean, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)
Autofits a range of rows so they adapt their height to show all the text inside\. Note that due to GDI\+ / GDI incompatibilities, the height calculated by FlexCel will not be exactly the same than the one calculated by Excel\. So when you open this workbook in Excel, Excel will re calculate the row heights to what it believes is best\.
You can change this behavior specifying keepHeightAutomatic = false\.
See also [Fine Tuning Row Autofitting](xref:FineTuningRowAutofitting)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitRow(const row1: Integer; const row2: Integer; const minCol: Integer; const maxCol: Integer; const autofitNotAutofittingRows: Boolean; const keepHeightAutomatic: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row to autofit\.|
|const|**row2**|Integer|Last row to autofit\.|
|const|**minCol**|Integer|First column that will be used to calculate the height of the row\. If for example you wanted to calculate the row height based in the contents of the columns 3 to 9, you would specify 3 here\.|
|const|**maxCol**|Integer|Last column that will be used to calculate the height of the row\. If for example you wanted to calculate the row height based in the contents of the columns 3 to 9, you would specify 9 here\.<br /><br />**Specify any value \<=0 here to use all columns for the autofit\.**|
|const|**autofitNotAutofittingRows**|Boolean|When you are autofitting a range of rows, some rows might not be  set to Autofit in Excel\. When this parameter is true, those rows will be autofitted anyway\.|
|const|**keepHeightAutomatic**|Boolean|If true, rows will be still autoheight when you open the file in Excel, so Excel will recalculate the values, probably changing the page breaks\. If you set it to false, rows will be fixed in size, and when you open it on Excel they will remain so\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which row in a merged cell using more than one row will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last row\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.AutofitCol
description: TExcelFile.AutofitCol
---

# TExcelFile\.AutofitCol Method

## Overloads

* [TExcelFile\.AutofitCol\(Integer, Boolean, Double\)](#texcelfileautofitcolinteger-boolean-double)
* [TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double\)](#texcelfileautofitcolinteger-integer-boolean-double)
* [TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double, Integer, Integer, Integer\)](#texcelfileautofitcolinteger-integer-boolean-double-integer-integer-integer)
* [TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitcolinteger-integer-boolean-double-integer-integer-integer-tautofitmerged)
* [TExcelFile\.AutofitCol\(Integer, Integer, Integer, Integer, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)](#texcelfileautofitcolinteger-integer-integer-integer-boolean-double-integer-integer-integer-tautofitmerged)

# TExcelFile\.AutofitCol\(Integer, Boolean, Double\)
Autofits a column so it adapts its width to show all the text inside\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitCol(const col: Integer; const ignoreStrings: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to Autofit\.|
|const|**ignoreStrings**|Boolean|When true, strings will not be considered for the autofit\. Only numbers will\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double\)
Autofits a range of columns so they adapt their width to show all the text inside\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitCol(const col1: Integer; const col2: Integer; const ignoreStrings: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column to Autofit\.|
|const|**col2**|Integer|Last column to Autofit\.|
|const|**ignoreStrings**|Boolean|When true, strings will not be considered for the autofit\. Only numbers will\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double, Integer, Integer, Integer\)
Autofits a range of columns so they adapt their width to show all the text inside\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitCol(const col1: Integer; const col2: Integer; const ignoreStrings: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minWidth: Integer; const maxWidth: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column to Autofit\.|
|const|**col2**|Integer|Last column to Autofit\.|
|const|**ignoreStrings**|Boolean|When true, strings will not be considered for the autofit\. Only numbers will\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the column will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the column and not a percentage\. The final size of the column will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minWidth**|Integer|Minimum final width for the column to autofit\. If the calculated value is less than minWidth, column size will be set to minWidth\.<br /><br />A negative value on minWidth means the column size will be no smaller than the original width\.|
|const|**maxWidth**|Integer|Maximum final width for the column to autofit\. If the calculated value is more than maxWidth, column size will be set to maxWidth\.<br /><br />maxWidth = 0 means no maxWidth\.<br /><br />A negative value on maxWidth means the column size will be no bigger than the original width\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitCol\(Integer, Integer, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)
Autofits a range of columns so they adapt their width to show all the text inside\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitCol(const col1: Integer; const col2: Integer; const ignoreStrings: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minWidth: Integer; const maxWidth: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column to Autofit\.|
|const|**col2**|Integer|Last column to Autofit\.|
|const|**ignoreStrings**|Boolean|When true, strings will not be considered for the autofit\. Only numbers will\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the column will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the column and not a percentage\. The final size of the column will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minWidth**|Integer|Minimum final width for the column to autofit\. If the calculated value is less than minWidth, column size will be set to minWidth\.<br /><br />A negative value on minWidth means the column size will be no smaller than the original width\.|
|const|**maxWidth**|Integer|Maximum final width for the column to autofit\. If the calculated value is more than maxWidth, column size will be set to maxWidth\.<br /><br />maxWidth = 0 means no maxWidth\.<br /><br />A negative value on maxWidth means the column size will be no bigger than the original width\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which column in a merged cell using more than one column will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last column\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.AutofitCol\(Integer, Integer, Integer, Integer, Boolean, Double, Integer, Integer, Integer, TAutofitMerged\)
Autofits a range of columns so they adapt their width to show all the text inside\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AutofitCol(const col1: Integer; const col2: Integer; const minRow: Integer; const maxRow: Integer; const ignoreStrings: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minWidth: Integer; const maxWidth: Integer; const autofitMerged: <a href="../TAutofitMerged.md">TAutofitMerged</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column to Autofit\.|
|const|**col2**|Integer|Last column to Autofit\.|
|const|**minRow**|Integer|First row that will be used to autofit the column\. If you want for example to autofit a column based only in the cells from row 3 to 10, you would use 3 as minRow\.|
|const|**maxRow**|Integer|Last row that will be used to autofit the column\. If you want for example to autofit a column based only in the cells from row 3 to 10, you would use 10 as maxRow\.<br /><br />**Specify any value \<=0 here to use all rows for the autofit\.**|
|const|**ignoreStrings**|Boolean|When true, strings will not be considered for the autofit\. Only numbers will\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the column will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the column and not a percentage\. The final size of the column will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minWidth**|Integer|Minimum final width for the column to autofit\. If the calculated value is less than minWidth, column size will be set to minWidth\.<br /><br />A negative value on minWidth means the column size will be no smaller than the original width\.|
|const|**maxWidth**|Integer|Maximum final width for the column to autofit\. If the calculated value is more than maxWidth, column size will be set to maxWidth\.<br /><br />maxWidth = 0 means no maxWidth\.<br /><br />A negative value on maxWidth means the column size will be no bigger than the original width\.<br />|
|const|**autofitMerged**|[TAutofitMerged](../TAutofitMerged.md)|Specifies which column in a merged cell using more than one column will be used to autofit the merged cell\.<br />If you don't specify this parameter, it will be the last column\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


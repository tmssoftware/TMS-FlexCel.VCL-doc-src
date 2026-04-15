---
uid: TExcelFile.MarkColForAutofit
description: TExcelFile.MarkColForAutofit
---

# TExcelFile\.MarkColForAutofit Method

## Overloads

* [TExcelFile\.MarkColForAutofit\(Integer, Boolean, Double\)](#texcelfilemarkcolforautofitinteger-boolean-double)
* [TExcelFile\.MarkColForAutofit\(Integer, Boolean, Double, Integer, Integer, Integer, Boolean\)](#texcelfilemarkcolforautofitinteger-boolean-double-integer-integer-integer-boolean)

# TExcelFile\.MarkColForAutofit\(Integer, Boolean, Double\)
Marks a column as candidate for future autofit\. Note that this method will NOT change anything on the file\. It just "marks" the column  so you can use it later with [AutofitMarkedRowsAndCols\(Boolean, Boolean, Double\)](AutofitMarkedRowsAndCols.md#texcelfileautofitmarkedrowsandcolsboolean-boolean-double)\.


## Remarks

You can use this method for "delay\-marking" columns that you will want to autofit later, but that you cannot autofit yet since they are not filled with data\.There is normally no need to use this method, but it is used on report generation to "mark" \<\#col width\(autofit\)> tags so those rows and columns can be autofitted once the data on the sheet has been filled\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.MarkColForAutofit(const col: Integer; const autofit: Boolean; const adjustment: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)|
|const|**autofit**|Boolean|Set this to true to mark the column for autofitting, false for removing the column from autofitting list\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.MarkColForAutofit\(Integer, Boolean, Double, Integer, Integer, Integer, Boolean\)
Marks a column as candidate for future autofit\. Note that this method will NOT change anything on the file\. It just "marks" the column  so you can use it later with [AutofitMarkedRowsAndCols\(Boolean, Boolean, Double\)](AutofitMarkedRowsAndCols.md#texcelfileautofitmarkedrowsandcolsboolean-boolean-double)\.


## Remarks

You can use this method for "delay\-marking" columns that you will want to autofit later, but that you cannot autofit yet since they are not filled with data\.There is normally no need to use this method, but it is used on report generation to "mark" \<\#col width\(autofit\)> tags so those rows and columns can be autofitted once the data on the sheet has been filled\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.MarkColForAutofit(const col: Integer; const autofit: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minWidth: Integer; const maxWidth: Integer; const isMerged: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)|
|const|**autofit**|Boolean|Set this to true to mark the column for autofitting, false for removing the column from autofitting list\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then columns will be adjusted to 110%% percent of what their calculated width was\.<br />Use this parameter to fine\-tune autofiting, if for example columns are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the column and not a percentage\. The final size of the column will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minWidth**|Integer|Minimum final width for the column to autofit\. If the calculated value is less than minWidth, column size will be set to minWidth\.<br /><br />A negative value on minWidth means the column size will be no smaller than the original width\.|
|const|**maxWidth**|Integer|Maximum final width for the column to autofit\. If the calculated value is more than maxWidth, column size will be set to maxWidth\.<br /><br />maxWidth = 0 means no maxWidth\.<br /><br />A negative value on maxWidth means the column size will be no bigger than the original width\.<br />|
|const|**isMerged**|Boolean|If true, only the cell will be autofitted, not the whole column\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


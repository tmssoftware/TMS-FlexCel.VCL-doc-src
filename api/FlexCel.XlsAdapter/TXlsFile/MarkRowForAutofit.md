---
uid: TXlsFile.MarkRowForAutofit
description: TXlsFile.MarkRowForAutofit
---

# TXlsFile\.MarkRowForAutofit Method

Marks a row as candidate for future autofit\. Note that this method will NOT change anything on the file\. It just "marks" the row  so you can use it later with [TExcelFile.AutofitMarkedRowsAndCols\(Boolean, Boolean, Double\)](../../FlexCel.Core/TExcelFile/AutofitMarkedRowsAndCols.md#texcelfileautofitmarkedrowsandcolsboolean-boolean-double)\. To change the actual autofit status on the xls file, use [TExcelFile.SetAutoRowHeight](../../FlexCel.Core/TExcelFile/SetAutoRowHeight.md)**NOTE**: This method will not mark empty rows\.


## Remarks

You can use this method for "delay\-marking" rows that you will want to autofit later, but that you cannot autofit yet since they are not filled with data\. There is normally no need to use this method, but it is used on report generation to "mark" \<\#row height\(autofit\)> tags so those rows and columns can be autofitted once the data on the sheet has been filled\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.MarkRowForAutofit(const row: Integer; const autofit: Boolean; const adjustment: Double; const adjustmentFixed: Integer; const minHeight: Integer; const maxHeight: Integer; const isMerged: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1 based\)|
|const|**autofit**|Boolean|Set this to true to mark the row for autofitting, false for removing the row from autofitting list\.|
|const|**adjustment**|Double|You will normally want to set this parameter to 1, which means that autofit will be made with standard measurements\.<br />If you set it to for example 1\.1, then rows will be adjusted to 110%% percent of what their calculated height was\.<br />Use this parameter to fine\-tune autofiting, if for example rows are too small when opening the file in Excel\.|
|const|**adjustmentFixed**|Integer|You will normally set this parameter to 0, which means standard autofit\. If you set it to a value, the row will be made larger by that amount from the calculated autofit\. Different from the "adjustment" parameter, this parameter adds a fixed size to the row and not a percentage\. The final size of the row will be:  FinalSize = CalulatedAutoFit \* adjustment \+ adjusmentFixed|
|const|**minHeight**|Integer|Minimum final height for the row to autofit\. If the calculated value is less than minHeight, row size will be set to minHeight\.<br /><br />A negative value on minHeight means the row size will be no smaller than the original height\.|
|const|**maxHeight**|Integer|Maximum final height for the row to autofit\. If the calculated value is more than maxHeight, row size will be set to maxHeight\.<br /><br />maxHeight = 0 means no maxHeight\.<br /><br />A negative value on maxHeight means the row size will be no bigger than the original height\.<br />|
|const|**isMerged**|Boolean|If true, only the cell will be autofitted, not the whole row\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


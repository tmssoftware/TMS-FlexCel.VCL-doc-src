---
uid: TExcelFile.RecalcRange
description: TExcelFile.RecalcRange
---

# TExcelFile\.RecalcRange Method

This method recalculates a formula that returns a range, and returns the cells that compose it\. Note that normally ranges are a single rectangle \(like in "=A1:B2"\), and in this case this method will return a single element in the array\.
But you might have a formula like "=A1:A10, C6:C7" which will return two different ranges\. In this case, the returned array will have more than one TCellAddressRange\.
If the formula doesn't resolve to a range or group of ranges, this method will return null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcRange(const activeSheet: Integer; const activeRow: Integer; const activeCol: Integer; const rowOffset: Integer; const colOffset: Integer; const expression: string; const forced: Boolean; const relativeReferences: Boolean): TArray&lt;<a href="../TCellAddressRange/index.md">TCellAddressRange</a>&gt;; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**activeSheet**|Integer|Sheet where you are positioned when doing the calculation\. You might pass xls\.ActiveSheet here\.|
|const|**activeRow**|Integer|Row where you are positioned when doing the calculation\. This only matters if you have functions that change depending on the cell you are in\. \(Mainly =Row\(\) and =Column\(\) functions\)\.<br />If you are not sure, specify 1 here\.|
|const|**activeCol**|Integer|Column where you are positioned when doing the calculation\. This only matters if you have functions that change depending on the cell you are in\. \(Mainly =Row\(\) and =Column\(\) functions\)\.<br />If you are not sure, specify 1 here\.|
|const|**rowOffset**|Integer|Offset from the first cell of a range\. This only matters if you have relative references that change depending on the cell you are in\. \(This is the case with named ranges or data validations and relative references like A1 instead of $A$1\)\.<br />If you are not sure, specify 0 here\.|
|const|**colOffset**|Integer|Offset from the first cell of a range\. This only matters if you have relative references that change depending on the cell you are in\. \(This is the case with named ranges or data validations and relative references like A1 instead of $A$1\)\.<br />If you are not sure, specify 0 here\.|
|const|**expression**|string|Formula to evaluate\. It must start with "=", be a valid Excel formula and resolve to a range of cells\.|
|const|**forced**|Boolean|When true this method will always perform a recalc\. When false, only if there has been a change on the spreadsheet\.<br />While for performance reasons you will normally want to keep this false, you might need to set it to true if the formulas refer to functions like "=NOW\(\)" or "=RANDOM\(\)" that change every time you recalculate\.|
|const|**relativeReferences**|Boolean|Specifies if the references in the formula are relative to the cell where the cursor is positioned or not\. Formulas in data validations, name definitions and conditional formats are relative and should have this parameter set to true\. Formulas in cell are not relative, and should have this parameter set to false\.|


## Returns

The array of ranges that the formula refers to\.

## See also

* [TExcelFile](../TExcelFile/index.md)


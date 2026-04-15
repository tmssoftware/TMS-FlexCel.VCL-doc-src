---
uid: TExcelFile.InsertAndCopySheets
description: TExcelFile.InsertAndCopySheets
---

# TExcelFile\.InsertAndCopySheets Method

## Overloads

* [TExcelFile\.InsertAndCopySheets\(Integer, Integer, Integer\)](#texcelfileinsertandcopysheetsinteger-integer-integer)
* [TExcelFile\.InsertAndCopySheets\(Int32Array, Integer, TExcelFile\)](#texcelfileinsertandcopysheetsint32array-integer-texcelfile)
* [TExcelFile\.InsertAndCopySheets\(Integer, Integer, Integer, TExcelFile\)](#texcelfileinsertandcopysheetsinteger-integer-integer-texcelfile)

# TExcelFile\.InsertAndCopySheets\(Integer, Integer, Integer\)
Inserts and copies sheet "CopyFrom", SheetCount times before InsertBefore\.
To insert empty sheets, set CopyFrom = 0 \(You might also call [AddSheet](AddSheet.md)\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.InsertAndCopySheets(const copyFrom: Integer; const insertBefore: Integer; const aSheetCount: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**copyFrom**|Integer|The sheet index of the sheet we are copying from \(1 based\)\. Set it to 0 to insert Empty sheets\.|
|const|**insertBefore**|Integer|The sheet before which we will insert \(1 based\)\. This might be SheetCount \+ 1, to insert at the end of the Workbook\.|
|const|**aSheetCount**|Integer|How many times the sheet copyFrom will be copied\. Note that this is \*\*not\*\* the last sheet to be copied, but how many times a single sheet will be copied instead\. This means that for example InsertAndCopySheets\(3, 1, 7\) will insert 7 copies of sheet 3, not copy sheets 3 to 10\. To copy multiple sheets see [InsertAndCopySheets\(Int32Array, Integer, TExcelFile\)](InsertAndCopySheets.md#texcelfileinsertandcopysheetsint32array-integer-texcelfile)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.InsertAndCopySheets\(Int32Array, Integer, TExcelFile\)
Inserts and copies all the sheets in the "CopyFrom" array, before InsertBefore into another workbook\.


## Remarks

When copying sheets from another file, the algorithm used is not so efficient as when copying from the same file\.





Use this version of the method only when copying from 2 different files\. If you have for example a formula "=Sheet2\!A1" in Sheet1, and another formula "=Sheet1\!A1" in Sheet2, you need to use this method to copy them, as Copying them one by one \(with the standard [InsertAndCopySheets\(Integer, Integer, Integer, TExcelFile\)](InsertAndCopySheets.md#texcelfileinsertandcopysheetsinteger-integer-integer-texcelfile) method\) will return an error of formula references not found\.





You can also use [ConvertFormulasToValues\(Boolean\)](ConvertFormulasToValues.md#texcelfileconvertformulastovaluesboolean) method to avoid formulas before copying between workbooks\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.InsertAndCopySheets(const copyFrom: TArray&lt;Int32>; const insertBefore: Integer; const sourceWorkbook: <a href="../TExcelFile/index.md">TExcelFile</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**copyFrom**|TArray\<Int32>|The sheet index of all the sheets we are copying from \(1 based\)\.|
|const|**insertBefore**|Integer|The sheet before which we will insert \(1 based\)\. This might be SheetCount\+1, to insert at the end of the Workbook\.|
|const|**sourceWorkbook**|[TExcelFile](../TExcelFile/index.md)|Workbook from where the sheet will be copied from\. On this overloaded version it cannot be null\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.InsertAndCopySheets\(Integer, Integer, Integer, TExcelFile\)
Inserts and copies sheet "CopyFrom", SheetCount times before InsertBefore\.
If sourceWorkbook is not null, sheets will be copied from another file\.
To insert empty sheets, set CopyFrom=0\.


## Remarks

When copying sheets from another file, the algorithm used is not so efficient as when copying from the same file\. Whenever possible, don't copy from different files\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.InsertAndCopySheets(const copyFrom: Integer; const insertBefore: Integer; const aSheetCount: Integer; const sourceWorkbook: <a href="../TExcelFile/index.md">TExcelFile</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**copyFrom**|Integer|The sheet index of the sheet we are copying from \(1 based\)\. Set it to 0 to insert Empty sheets\.|
|const|**insertBefore**|Integer|The sheet before which we will insert \(1 based\)\. This might be SheetCount\+1, to insert at the end of the Workbook\.|
|const|**aSheetCount**|Integer|How many times the sheet copyFrom will be copied\. Note that this is \*\*not\*\* the last sheet to be copied, but how many times a single sheet will be copied instead\. This means that for example InsertAndCopySheets\(3, 1, 7\) will insert 7 copies of sheet 3, not copy sheets 3 to 10\. To copy multiple sheets see [InsertAndCopySheets\(Int32Array, Integer, TExcelFile\)](InsertAndCopySheets.md#texcelfileinsertandcopysheetsint32array-integer-texcelfile)|
|const|**sourceWorkbook**|[TExcelFile](../TExcelFile/index.md)|Workbook from where the sheet will be copied from\. Null to copy from the same file\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.CopyCell
description: TExcelFile.CopyCell
---

# TExcelFile\.CopyCell Method

Copies **one** cell from one workbook to another\. If the cell has a formula, it will be offset so it matches the new destination\.
**Note:** You will normally not need this method\. To copy a range of cells from a workbook to another use  [InsertAndCopyRange\(TXlsCellRange, Integer, Integer, Integer, TFlxInsertMode, TRangeCopyMode, TExcelFile, Integer\)](InsertAndCopyRange.md#texcelfileinsertandcopyrangetxlscellrange-integer-integer-integer-tflxinsertmode-trangecopymode-texcelfile-integer) instead\.
To copy a full sheet from one file to another, use [InsertAndCopySheets\(Integer, Integer, Integer, TExcelFile\)](InsertAndCopySheets.md#texcelfileinsertandcopysheetsinteger-integer-integer-texcelfile)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.CopyCell(const sourceWorkbook: <a href="../TExcelFile/index.md">TExcelFile</a>; const sourceSheet: Integer; const destSheet: Integer; const sourceRow: Integer; const sourceCol: Integer; const destRow: Integer; const destCol: Integer; const copyMode: <a href="../TRangeCopyMode.md">TRangeCopyMode</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceWorkbook**|[TExcelFile](../TExcelFile/index.md)|File from where we want to copy the cell\.|
|const|**sourceSheet**|Integer|Sheet in sourceWorkbook where the data is\.|
|const|**destSheet**|Integer|Sheet in this file where we want to copy the data\.|
|const|**sourceRow**|Integer|Row on the source file of the cell \(1 based\)|
|const|**sourceCol**|Integer|Column on the source file of the cell \(1 based\)|
|const|**destRow**|Integer|Row on the destination file of the cell \(1 based\)|
|const|**destCol**|Integer|Column on the destination file of the cell \(1 based\)|
|const|**copyMode**|[TRangeCopyMode](../TRangeCopyMode.md)|How the cell will be copied\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


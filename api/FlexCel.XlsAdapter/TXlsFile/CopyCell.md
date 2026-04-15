---
uid: TXlsFile.CopyCell
description: TXlsFile.CopyCell
---

# TXlsFile\.CopyCell Method

Copies **one** cell from one workbook to another\. If the cell has a formula, it will be offset so it matches the new destination\.
**Note:** You will normally not need this method\. To copy a range of cells from a workbook to another use  [TExcelFile.InsertAndCopyRange\(TXlsCellRange, Integer, Integer, Integer, TFlxInsertMode, TRangeCopyMode, TExcelFile, Integer\)](../../FlexCel.Core/TExcelFile/InsertAndCopyRange.md#texcelfileinsertandcopyrangetxlscellrange-integer-integer-integer-tflxinsertmode-trangecopymode-texcelfile-integer) instead\.
To copy a full sheet from one file to another, use [TExcelFile.InsertAndCopySheets\(Integer, Integer, Integer, TExcelFile\)](../../FlexCel.Core/TExcelFile/InsertAndCopySheets.md#texcelfileinsertandcopysheetsinteger-integer-integer-texcelfile)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CopyCell(const sourceWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const sourceSheet: Integer; const destSheet: Integer; const sourceRow: Integer; const sourceCol: Integer; const destRow: Integer; const destCol: Integer; const copyMode: <a href="../../FlexCel.Core/TRangeCopyMode.md">TRangeCopyMode</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|File from where we want to copy the cell\.|
|const|**sourceSheet**|Integer|Sheet in sourceWorkbook where the data is\.|
|const|**destSheet**|Integer|Sheet in this file where we want to copy the data\.|
|const|**sourceRow**|Integer|Row on the source file of the cell \(1 based\)|
|const|**sourceCol**|Integer|Column on the source file of the cell \(1 based\)|
|const|**destRow**|Integer|Row on the destination file of the cell \(1 based\)|
|const|**destCol**|Integer|Column on the destination file of the cell \(1 based\)|
|const|**copyMode**|[TRangeCopyMode](../../FlexCel.Core/TRangeCopyMode.md)|How the cell will be copied\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


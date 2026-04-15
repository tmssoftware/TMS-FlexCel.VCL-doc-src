---
uid: TXlsFile.MoveRange
description: TXlsFile.MoveRange
---

# TXlsFile\.MoveRange Method

Moves a range of cells, the same way Excel does it\. All references pointing to the old range will be relocated to the new, and all existing references to the new range will be relocated to \#ref\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.MoveRange(const cellRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const newRow: Integer; const newCol: Integer; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>; const fixAllFormulas: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range you want to move\.|
|const|**newRow**|Integer|Row where the range will be relocated\.|
|const|**newCol**|Integer|Column where the range will be relocated\.|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|This parameter switches between 2 different working modes:<br />* Modes NoneDown and NoneRight are the same, and work the same way as when you drag a range of cells in Excel to  a new location\. Cells on the new range will be replaced by the old, and cells where the old range was located will be cleared\(not deleted\)\.<br />No cells are inserted or deleted\.<br /><br />* The other modes behave like when you select a range in Excel, cut it, and then right click and select "Insert Cut Cells\.\.\."\. The old range will be inserted where the new range goes, cells where the old range was will be deleted\(not cleared\)\.<br />Using for example MoveRange\(CellRange, newRow, newCol, TFlxInsertMode\.ShiftRight\) is equivalent to: 1\) InsertAndCopyRange\(CellRange, newRow, newCol, 1, TFlxInsertMode\.ShiftRight, TRangeCopyMode\.None\);  2\) MoveRange\(CellRange, newRow, newCol, TFlxInsertMode\.NoneRight\);   3\) DeleteRange\(CellRange, TFlxInsertMode\.ShiftRight\);<br /><br />|
|const|**fixAllFormulas**|Boolean|If true \(the default\) FlexCel will correctly adapt all the references in all formulas everywhere\. If false only the formulas being moved will be changed\. The results with this parameter = false are incorrect if you have formulas pointing to the range moved, but is faster if you know no formulas point to cells inside the range moved\.<br />You should normally keep this parameter = true\. FlexCel uses it false to emulate the way Excel sorts \(which is wrong\)\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


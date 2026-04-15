---
uid: TXlsFile.InsertAndCopyRange
description: TXlsFile.InsertAndCopyRange
---

# TXlsFile\.InsertAndCopyRange Method

Inserts and/or copies a range of cells from one place to another\.

This method is one of the most important on FlexCel API, and it allows you to copy ranges of cells from one place to another, adapting the formulas, images and everything as Excel would do it\.


## Remarks

This overload is useful for **copying from another file\.** It is not as fast or complete as the other overloaded versions because it has to do a lot of transforms on the data\. But it is very useful anyway\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.InsertAndCopyRange(const sourceRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const destRow: Integer; const destCol: Integer; const destCount: Integer; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>; const copyMode: <a href="../../FlexCel.Core/TRangeCopyMode.md">TRangeCopyMode</a>; const sourceWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const sourceSheet: Integer; const ObjectsInRange: <a href="../../FlexCel.Core/TExcelObjectList/index.md">TExcelObjectList</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|The range of cells you want to copy\. If you specify full rows, they will be copied with Row format information and size\. If you copy just a part of a row, Row format will not be copied\.<br />The same applies to columns\. The only way to copy **all** row and columns, is to specify the full \(A:IV\) range\.|
|const|**destRow**|Integer|Destination row where the cells will be copied\.|
|const|**destCol**|Integer|Destination column where the cells will be copied\.|
|const|**destCount**|Integer|Number of times the sourceRange will be copied at \(desRow, destCol\)\.<br />If you make for example destCount=2, sourceRange will be copied 2 times at \(destRow, destCol\)|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|How the cells on destination will be inserted\. They can shift down or left\.<br />Specifying Row or Col as mode is equivalent to specify a sourceRange including full rows or columns respectively\.|
|const|**copyMode**|[TRangeCopyMode](../../FlexCel.Core/TRangeCopyMode.md)|Which cells on sourceRange will be copied\. If you intend to replace values on the copied cells, you might specify OnlyFormulas\. If you just want to **insert** cells and not copy, specify None\.|
|const|**sourceWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|Workbook from where we are copying the cells\. This might be the same workbook, and you would by copying from another sheet\.|
|const|**sourceSheet**|Integer|Sheet index on the source workbook\. If sourceWorkbook is the same instance as this, and sourceSheet is the active sheet on the instance, this method is equivalent to the simpler overloaded version\.|
|const|**ObjectsInRange**|[TExcelObjectList](../../FlexCel.Core/TExcelObjectList/index.md)|Returns the objects that are in the range to be copied\. This is an optimization so you don't have to find those objects again\. Set it to null to not return any objects|


## See also

* [TXlsFile](../TXlsFile/index.md)


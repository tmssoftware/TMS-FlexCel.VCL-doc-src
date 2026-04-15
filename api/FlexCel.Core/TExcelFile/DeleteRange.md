---
uid: TExcelFile.DeleteRange
description: TExcelFile.DeleteRange
---

# TExcelFile\.DeleteRange Method

## Overloads

* [TExcelFile\.DeleteRange\(TXlsCellRange, TFlxInsertMode\)](#texcelfiledeleterangetxlscellrange-tflxinsertmode)
* [TExcelFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode\)](#texcelfiledeleterangeinteger-integer-txlscellrange-tflxinsertmode)
* [TExcelFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode, Boolean\)](#texcelfiledeleterangeinteger-integer-txlscellrange-tflxinsertmode-boolean)

# TExcelFile\.DeleteRange\(TXlsCellRange, TFlxInsertMode\)
Deletes a range of cells, and moves all cells below up or all cells to the right left, depending on the insert mode\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteRange(const cellRange: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to delete\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|Mode of deletion\. Note that Row and Col are equivalent to ShiftRight and ShiftDown with a  cell range of full rows or cols respectively\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode\)
Deletes a range of cells, and moves all cells below up or all cells to the right left, depending on the insert mode\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteRange(const sheet1: Integer; const sheet2: Integer; const cellRange: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet1**|Integer|First sheet where to delete cells\.|
|const|**sheet2**|Integer|Last sheet where to delete cells\.|
|const|**cellRange**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to delete\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|Mode of deletion\. Note that Row and Col are equivalent to ShiftRight and ShiftDown with a  cell range of full rows or cols respectively\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode, Boolean\)
Deletes a range of cells, and moves all cells below up or all cells to the right left, depending on the insert mode\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteRange(const sheet1: Integer; const sheet2: Integer; const cellRange: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>; const removeFormats: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet1**|Integer|First sheet where to delete cells\.|
|const|**sheet2**|Integer|Last sheet where to delete cells\.|
|const|**cellRange**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells to delete\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|Mode of deletion\. Note that Row and Col are equivalent to ShiftRight and ShiftDown with a  cell range of full rows or cols respectively\.|
|const|**removeFormats**|Boolean|If true, both formatting and data will be removed from the range, when clearing a range\.<br />This parameter has no effect if insertmode isn't one of the "none" options, because if it isn't the full range will move up or left\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.DeleteRange
description: TXlsFile.DeleteRange
---

# TXlsFile\.DeleteRange Method

## Overloads

* [TXlsFile\.DeleteRange\(TXlsCellRange, TFlxInsertMode\)](#txlsfiledeleterangetxlscellrange-tflxinsertmode)
* [TXlsFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode, Boolean\)](#txlsfiledeleterangeinteger-integer-txlscellrange-tflxinsertmode-boolean)

# TXlsFile\.DeleteRange\(TXlsCellRange, TFlxInsertMode\)
Deletes a range of cells, and moves all cells below up or all cells to the right left, depending on the insert mode\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteRange(const cellRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells to delete\.|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|Mode of deletion\. Note that Row and Col are equivalent to ShiftRight and ShiftDown with a  cell range of full rows or cols respectively\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.DeleteRange\(Integer, Integer, TXlsCellRange, TFlxInsertMode, Boolean\)
Deletes a range of cells, and moves all cells below up or all cells to the right left, depending on the insert mode\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteRange(const sheet1: Integer; const sheet2: Integer; const cellRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>; const removeFormats: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet1**|Integer|First sheet where to delete cells\.|
|const|**sheet2**|Integer|Last sheet where to delete cells\.|
|const|**cellRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells to delete\.|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|Mode of deletion\. Note that Row and Col are equivalent to ShiftRight and ShiftDown with a  cell range of full rows or cols respectively\.|
|const|**removeFormats**|Boolean|If true, both formatting and data will be removed from the range, when clearing a range\.<br />This parameter has no effect if insertmode isn't one of the "none" options, because if it isn't the full range will move up or left\.<br />|


## See also

* [TXlsFile](../TXlsFile/index.md)


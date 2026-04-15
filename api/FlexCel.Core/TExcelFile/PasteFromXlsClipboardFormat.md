---
uid: TExcelFile.PasteFromXlsClipboardFormat
description: TExcelFile.PasteFromXlsClipboardFormat
---

# TExcelFile\.PasteFromXlsClipboardFormat Method

## Overloads

* [TExcelFile\.PasteFromXlsClipboardFormat\(Integer, Integer, TFlxInsertMode, TStream\)](#texcelfilepastefromxlsclipboardformatinteger-integer-tflxinsertmode-tstream)
* [TExcelFile\.PasteFromXlsClipboardFormat\(Integer, Integer, TFlxInsertMode, TStream, Boolean\)](#texcelfilepastefromxlsclipboardformatinteger-integer-tflxinsertmode-tstream-boolean)

# TExcelFile\.PasteFromXlsClipboardFormat\(Integer, Integer, TFlxInsertMode, TStream\)
Pastes the clipboard contents beginning on cells row, col\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.PasteFromXlsClipboardFormat(const row: Integer; const col: Integer; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>; const data: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First row where to paste\.|
|const|**col**|Integer|First column where to paste\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|How the pasted cells will be inserted on the file\.|
|const|**data**|TStream|A stream containing a Native xls format\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.PasteFromXlsClipboardFormat\(Integer, Integer, TFlxInsertMode, TStream, Boolean\)
Pastes the clipboard contents beginning on cells row, col, with the option to convert formulas to their values\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.PasteFromXlsClipboardFormat(const row: Integer; const col: Integer; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>; const data: TStream; const convertFormulasToValues: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First row where to paste\.|
|const|**col**|Integer|First column where to paste\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|How the pasted cells will be inserted on the file\.|
|const|**data**|TStream|A stream containing a Native xls format\.|
|const|**convertFormulasToValues**|Boolean|If true, the formulas will be converted to values\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


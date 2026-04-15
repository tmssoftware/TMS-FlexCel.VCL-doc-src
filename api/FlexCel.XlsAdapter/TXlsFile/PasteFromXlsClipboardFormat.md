---
uid: TXlsFile.PasteFromXlsClipboardFormat
description: TXlsFile.PasteFromXlsClipboardFormat
---

# TXlsFile\.PasteFromXlsClipboardFormat Method

Pastes the clipboard contents beginning on cells row, col, with the option to convert formulas to their values\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.PasteFromXlsClipboardFormat(const row: Integer; const col: Integer; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>; const data: TStream; const convertFormulasToValues: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First row where to paste\.|
|const|**col**|Integer|First column where to paste\.|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|How the pasted cells will be inserted on the file\.|
|const|**data**|TStream|A stream containing a Native xls format\.|
|const|**convertFormulasToValues**|Boolean|If true, the formulas will be converted to values\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


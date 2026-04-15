---
uid: TXlsFile.PasteFromTextClipboardFormat
description: TXlsFile.PasteFromTextClipboardFormat
---

# TXlsFile\.PasteFromTextClipboardFormat Method

Pastes the clipboard contents beginning on cells row, col\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.PasteFromTextClipboardFormat(const row: Integer; const col: Integer; const insertMode: <a href="../../FlexCel.Core/TFlxInsertMode.md">TFlxInsertMode</a>; const data: string); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First row where to paste\.|
|const|**col**|Integer|First column where to paste\.|
|const|**insertMode**|[TFlxInsertMode](../../FlexCel.Core/TFlxInsertMode.md)|How the pasted cells will be inserted on the file\.|
|const|**data**|string|A string containing a tab separated text format\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


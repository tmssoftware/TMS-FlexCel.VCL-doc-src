---
uid: TExcelFile.PasteFromTextClipboardFormat
description: TExcelFile.PasteFromTextClipboardFormat
---

# TExcelFile\.PasteFromTextClipboardFormat Method

Pastes the clipboard contents beginning on cells row, col\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.PasteFromTextClipboardFormat(const row: Integer; const col: Integer; const insertMode: <a href="../TFlxInsertMode.md">TFlxInsertMode</a>; const data: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|First row where to paste\.|
|const|**col**|Integer|First column where to paste\.|
|const|**insertMode**|[TFlxInsertMode](../TFlxInsertMode.md)|How the pasted cells will be inserted on the file\.|
|const|**data**|string|A string containing a tab separated text format\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


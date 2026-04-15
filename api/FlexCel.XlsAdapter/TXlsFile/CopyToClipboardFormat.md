---
uid: TXlsFile.CopyToClipboardFormat
description: TXlsFile.CopyToClipboardFormat
---

# TXlsFile\.CopyToClipboardFormat Method

Copies a range on the active sheet to a clipboard stream, on the specified format\.


## Remarks

See the copy and paste demo\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CopyToClipboardFormat(const clipboardFormat: <a href="../../FlexCel.Core/TFlexCelClipboardFormat.md">TFlexCelClipboardFormat</a>; const range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const outStream: TStream); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**clipboardFormat**|[TFlexCelClipboard&#8203;Format](../../FlexCel.Core/TFlexCelClipboardFormat.md)|Format you want to copy into outStream\.|
|const|**range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range with the cells to copy\.|
|const|**outStream**|TStream|Stream where the clipboard info will be copied\. If null, nothing will be copied\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.RenameStyle
description: TXlsFile.RenameStyle
---

# TXlsFile\.RenameStyle Method

Renames an existing style\. Note that this might be a user\-defined style, you can't rename built\-in styles\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.RenameStyle(const oldName: string; const newName: string); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**oldName**|string|Name of the existing style in the workbook\.|
|const|**newName**|string|New name for the style\. It must not exist\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


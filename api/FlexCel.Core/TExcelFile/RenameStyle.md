---
uid: TExcelFile.RenameStyle
description: TExcelFile.RenameStyle
---

# TExcelFile\.RenameStyle Method

Renames an existing style\. Note that this might be a user\-defined style, you can't rename built\-in styles\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenameStyle(const oldName: string; const newName: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**oldName**|string|Name of the existing style in the workbook\.|
|const|**newName**|string|New name for the style\. It must not exist\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


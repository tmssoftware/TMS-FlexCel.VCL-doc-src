---
uid: TXlsFile.AddButton
description: TXlsFile.AddButton
---

# TXlsFile\.AddButton Method

Adds a button to the sheet, with the associated macro\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AddButton(const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const name: string; const macro: string): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)|Position for the button\.|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text that will be shown in the button\.|
|const|**name**|string|Name for the inserted button\.|
|const|**macro**|string|Macro associated with the button\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


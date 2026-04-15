---
uid: TExcelFile.AddButton
description: TExcelFile.AddButton
---

# TExcelFile\.AddButton Method

Adds a button to the sheet, with the associated macro\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.AddButton(const anchor: <a href="../TClientAnchor/index.md">TClientAnchor</a>; const text: <a href="../TRichString/index.md">TRichString</a>; const name: string; const macro: string): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**anchor**|[TClientAnchor](../TClientAnchor/index.md)|Position for the button\.|
|const|**text**|[TRichString](../TRichString/index.md)|Text that will be shown in the button\.|
|const|**name**|string|Name for the inserted button\.|
|const|**macro**|string|Macro associated with the button\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


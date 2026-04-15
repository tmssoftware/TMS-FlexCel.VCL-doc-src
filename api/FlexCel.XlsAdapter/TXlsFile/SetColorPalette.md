---
uid: TXlsFile.SetColorPalette
description: TXlsFile.SetColorPalette
---

# TXlsFile\.SetColorPalette Method

Changes a color on the Excel color palette\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColorPalette(const index: Integer; const value: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the entry to change\. Must be 1\<=indexlt;=[TExcelFile.ColorPaletteCount](../../FlexCel.Core/TExcelFile/ColorPaletteCount.md)|
|const|**value**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color to set\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.PaletteContainsColor
description: TXlsFile.PaletteContainsColor
---

# TXlsFile\.PaletteContainsColor Method

Returns true if the internal color palette contains the exact specified color\. Note that Excel 2007 doesn't use the color palette, so this method is not needed there\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.PaletteContainsColor(const value: <a href="../../FlexCel.Core/TExcelColor/index.md">TExcelColor</a>): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TExcelColor](../../FlexCel.Core/TExcelColor/index.md)|Color to check\.|


## Returns

True if color is defined\.

## See also

* [TXlsFile](../TXlsFile/index.md)


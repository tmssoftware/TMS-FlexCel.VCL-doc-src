---
uid: TExcelFile.PaletteContainsColor
description: TExcelFile.PaletteContainsColor
---

# TExcelFile\.PaletteContainsColor Method

Returns true if the internal color palette contains the exact specified color\. Note that Excel 2007 doesn't use the color palette, so this method is not needed there\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.PaletteContainsColor(const value: <a href="../TExcelColor/index.md">TExcelColor</a>): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TExcelColor](../TExcelColor/index.md)|Color to check\.|


## Returns

True if color is defined\.

## See also

* [TExcelFile](../TExcelFile/index.md)


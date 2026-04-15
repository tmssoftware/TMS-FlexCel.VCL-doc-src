---
uid: TXlsFile.GetColorPalette
description: TXlsFile.GetColorPalette
---

# TXlsFile\.GetColorPalette Method

Returns a color from the color palette\. This method will throw an exception if its "index" parameter is bigger than [TExcelFile.ColorPaletteCount](../../FlexCel.Core/TExcelFile/ColorPaletteCount.md), \(for example, for an automatic color\)\.
To get the real color, use [TExcelFile.GetColorPalette\(Integer, TUIColor\)](../../FlexCel.Core/TExcelFile/GetColorPalette.md#texcelfilegetcolorpaletteinteger-tuicolor)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColorPalette(const index: Integer): <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the entry to return\. Must be 1\<=index\<=[TExcelFile.ColorPaletteCount](../../FlexCel.Core/TExcelFile/ColorPaletteCount.md)|


## Returns

Color at position index\.

## See also

* [TXlsFile](../TXlsFile/index.md)


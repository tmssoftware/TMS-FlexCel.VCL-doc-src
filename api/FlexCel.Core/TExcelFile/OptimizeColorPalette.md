---
uid: TExcelFile.OptimizeColorPalette
description: TExcelFile.OptimizeColorPalette
---

# TExcelFile\.OptimizeColorPalette Method

Changes the colors in the color palette so they can represent better the colors in use\. This method will change the colors not used in the palette by colors used in the sheet\. If there are more unique colors in the sheet than the 56 available in the palette, only the first colors will be changed\.


When FlexCel saves an xls file, it saves the color information twice: The real color for Excel 2007 and newer, and the indexed color for older Excel versions\. This method optimizes the palette of indexed colors so they look better in Excel 2003 or older\. It doesn't effect Excel 2007 or newer at all\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.OptimizeColorPalette; virtual; abstract;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


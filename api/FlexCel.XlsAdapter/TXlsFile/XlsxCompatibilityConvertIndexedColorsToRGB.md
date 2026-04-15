---
uid: TXlsFile.XlsxCompatibilityConvertIndexedColorsToRGB
description: TXlsFile.XlsxCompatibilityConvertIndexedColorsToRGB
---

# TXlsFile.XlsxCompatibilityConvertIndexedColorsToRGB Property

By default, if an xls or xlsx file has indexed colors or if you set an indexed color with the FlexCelAPI, FlexCel will save those colors as indexed in the final file\.
This is correct and the default, but LibreOffice/OpenOffice at the time of this writing \(version 6\.2\) won't understand indexed colors in xlsx files\. So if you have xlsx files with indexed colors that you want to display correctly in Libre/OpenOffice, you must turn this property on\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.XlsxCompatibilityConvertIndexedColorsToRGB: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


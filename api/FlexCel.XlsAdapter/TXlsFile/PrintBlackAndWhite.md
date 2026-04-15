---
uid: TXlsFile.PrintBlackAndWhite
description: TXlsFile.PrintBlackAndWhite
---

# TXlsFile.PrintBlackAndWhite Property

If true, page will be printed in "Excel Black and White"\.
**Important**: This property doesn't mean that the file will be printed in black and white\. Instead it means the option in the Page Setup dialog: [https://support.microsoft.com/en-us/office/page-setup-71c20d94-b13e-48fd-9800-cedd1fec6da3](https://support.microsoft.com/en-us/office/page-setup-71c20d94-b13e-48fd-9800-cedd1fec6da3)
Basically, when you select this option no background will be printed, and all foreground colors will be black\. So if you have a cell with a black background and a white font, it will print as white background with a black font\.


This property modifies [TExcelFile.PrintOptions](../../FlexCel.Core/TExcelFile/PrintOptions.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.PrintBlackAndWhite: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


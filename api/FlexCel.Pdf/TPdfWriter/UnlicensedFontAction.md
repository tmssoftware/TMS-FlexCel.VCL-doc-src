---
uid: TPdfWriter.UnlicensedFontAction
description: TPdfWriter.UnlicensedFontAction
---

# TPdfWriter.UnlicensedFontAction Property

Defines what to do when a font has a license that doesn't allow embedding, and you are trying to embed the font\.
FlexCel will default to throw an Exception in those cases, but if you for example have a license to embed the font, you can change this property to ignore the error\. You can also set a replacement font to be used for fonts that don't allow embedding inside PDF docs\. For more information, see [https://www.microsoft.com/en-us/microsoft-365/blog/2015/07/06/document-font-embedding-demystified/](https://www.microsoft.com/en-us/microsoft-365/blog/2015/07/06/document-font-embedding-demystified/)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.UnlicensedFontAction: <a href="../TUnlicensedFontAction.md">TUnlicensedFontAction</a></code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)


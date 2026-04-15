---
uid: TFlexCelPdfExport.FallbackFontsBold
description: TFlexCelPdfExport.FallbackFontsBold
---

# TFlexCelPdfExport.FallbackFontsBold Property

A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is bold\.

This property is only used for **bold** fonts, and has higher priority than [FallbackFonts](FallbackFonts.md) for bold fonts\.
It allows you to specify different fallback fonts for bold and not bold characters\.

**Important:** This property is only needed if the fonts in [FallbackFonts](FallbackFonts.md) don't have bold variants\.
If your fallback fonts come with bold variants, there is not need to set this property\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.FallbackFontsBold: string</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


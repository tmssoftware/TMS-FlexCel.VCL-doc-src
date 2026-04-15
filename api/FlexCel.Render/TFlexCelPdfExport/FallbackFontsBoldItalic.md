---
uid: TFlexCelPdfExport.FallbackFontsBoldItalic
description: TFlexCelPdfExport.FallbackFontsBoldItalic
---

# TFlexCelPdfExport.FallbackFontsBoldItalic Property

A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is bold and italic\.

This property is only used for fonts which are both **bold and***italic*, and has higher priority  than [FallbackFonts](FallbackFonts.md), [FallbackFontsBold](FallbackFontsBold.md) and [FallbackFontsItalic](FallbackFontsItalic.md) for bold\-italic fonts\.
It allows you to specify different fallback fonts for bold\-italic and not bold\-italic characters\.

**Important:** This property is only needed if the fonts in [FallbackFonts](FallbackFonts.md) don't have bold\-italic variants\.
If your fallback fonts come bold\-with italic variants, there is not need to set this property\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.FallbackFontsBoldItalic: string</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


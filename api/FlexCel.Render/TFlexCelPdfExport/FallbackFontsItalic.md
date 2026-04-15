---
uid: TFlexCelPdfExport.FallbackFontsItalic
description: TFlexCelPdfExport.FallbackFontsItalic
---

# TFlexCelPdfExport.FallbackFontsItalic Property

A semicolon \(;\) separated list of font names to try when a character is not found in the used font and the font is italic\.

This property is only used for *italic* fonts, and has higher priority than [FallbackFonts](FallbackFonts.md) for italic fonts\.
It allows you to specify different fallback fonts for italic and not italic characters\.

**Important:** This property is only needed if the fonts in [FallbackFonts](FallbackFonts.md) don't have italic variants\.
If your fallback fonts come with italic variants, there is not need to set this property\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.FallbackFontsItalic: string</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


---
uid: TFlexCelPdfExport.FallbackFonts
description: TFlexCelPdfExport.FallbackFonts
---

# TFlexCelPdfExport.FallbackFonts Property

A semicolon \(;\) separated list of font names to try when a character is not found in the used font\.

When a character is not found in a font, it will display as an empty square by default\. By setting this property, FlexCel will try to find a font that supports this character in this list, and if found, use that font to render the character\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.FallbackFonts: string</code></pre>

## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


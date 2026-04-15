---
uid: TPdfWriter.FallbackFonts
description: TPdfWriter.FallbackFonts
---

# TPdfWriter.FallbackFonts Property

A semicolon \(;\) separated list of font names to try when a character is not found in the used font\.

When a character is not found in a font, it will display as an empty square by default\. By setting this property, FlexCel will try to find a font that supports this character in this list, and if found, use that font to render the character\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.FallbackFonts: string</code></pre>

## Examples

You might set this property to "MS MINCHO;Arial Unicode MS"\. If a cell with font "Arial" has a character that is not in the "Arial" font, FlexCel will try to find the character first in MS Mincho, and if not found, in Arial Unicode\.

If it can find it in any of the fallback fonts, it will use that font in the pdf file\.


## See also

* [TPdfWriter](../TPdfWriter/index.md)


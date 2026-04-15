---
uid: TFlexCelConfig.ForcePdfFontsFromDisk
description: TFlexCelConfig.ForcePdfFontsFromDisk
---

# TFlexCelConfig.ForcePdfFontsFromDisk Property

If true, FlexCel will always try to load the fonts for rendering PDF Files from the disk\.
This allows you to use events like GetFontFolder or GetFontData to tell FlexCel where the fonts are\.
If this property is set to false \(the default\), then FlexCel will get the font definition directly from the Graphics engine, if the Graphics engine has a primitive to get the font data\. SKIA and CoreGraphics are 2 libraries that support getting the fonts directly\.


## Remarks

Try to not rely on fonts that are not available to the graphics engine, as it could cause issues, for example if the graphics engine tries to measure the font for something\.


If you set this property to true and provide the fonts to FlexCel via a [TPdfWriter.GetFontFolder](../../FlexCel.Pdf/TPdfWriter/GetFontFolder.md) event, the graphics engine powering FlexCel will not know about that font\.


So if possible, try to keep this property false, and make the fonts available to your app in a different way\.


For example in iOS, you can add the custom fonts to your app: https://developer\.apple\.com/documentation/uikit/text\_display\_and\_fonts/adding\_a\_custom\_font\_to\_your\_app and https://developer\.apple\.com/documentation/bundleresources/information\_property\_list/uiappfonts
You might also load those fonts to SKIA if using SKIA as backend\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelConfig/index.md">TFlexCelConfig</a>.ForcePdfFontsFromDisk: Boolean</code></pre>

## See also

* [TFlexCelConfig](../TFlexCelConfig/index.md)


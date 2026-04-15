---
uid: TFlexCelConfig
description: TFlexCelConfig
---

# TFlexCelConfig Record

A central point of for configuring FlexCel parameters\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelConfig = record;</code></pre>

## Properties

|Name|Description|
|---|---|
|[DpiForImages](DpiForImages.md)|Allows you to change the dpi for vector images \(metafiles\) when they are rasterized for converting to pdf / HTML / etc\. Note that this is a static setting and will affect all files\. This setting is the same as TExcelFile\.&#8203;Dpi&#8203;ForImages|
|[DpiForReadingImages](DpiForReadingImages.md)|Allows you to set a DPI for all images FlexCel is importing\. If this value is 0 \(the default\), then FlexCel will try to read the image resolution from the files themselves, if the files have a resolution saved\. If there is no resolution saved with the image, FlexCel will assume the images have the screen resolution\. When you set this property to a non 0 value \(like 96 for example\), then FlexCel will assume this is the resolution of the images it is reading, ignoring any resolution stored in the file\.<br />|
|[XlsxCompressionLevel](XlsxCompressionLevel.md)|Zip compression level when creating xlsx files\. This setting is the same as TExcelFile\.&#8203;XlsxCompression&#8203;Level\.&#8203;<br />Xlsx files are zip files, and you can compress more or less by trading speed for file size\. The faster you can create the file, the bigger the xlsx files created will be\.<br />Excel by default uses "Fastest" compression level and we use "Default"\. Normally using compression levels more than default is not worth it, since the files will take a lot longer to be created, and the size reduction will be very small\.<br />|
|[PdfPngCompression&#8203;Level](PdfPngCompressionLevel.md)|Zip compression level when creating pdf files or re encoding png images\.<br />Pds and Png files are zip files, and you can compress more or less by trading speed for file size\. The faster you can create the file, the bigger the pdf and png files created will be\.<br />Normally using compression levels more than default is not worth it, since the files will take a lot longer to be created, and the size reduction will be very small\.<br />|
|[ForcePdfFonts&#8203;From&#8203;Disk](ForcePdfFontsFromDisk.md)|If true, FlexCel will always try to load the fonts for rendering PDF Files from the disk\.<br />This allows you to use events like GetFontFolder or GetFontData to tell FlexCel where the fonts are\.<br />If this property is set to false \(the default\), then FlexCel will get the font definition directly from the Graphics engine, if the Graphics engine has a primitive to get the font data\. SKIA and CoreGraphics are 2 libraries that support getting the fonts directly\.<br />|
|[MaxFontsToCache](MaxFontsToCache.md)|Maximum number of fonts that can be cached in memory\.<br />|
|[MaxLambdaRecursion](MaxLambdaRecursion.md)|Maximum number of times that a name including a lambda function can refer to itself\.<br />|
|[LocalizedTEXTFunction](LocalizedTEXTFunction.md)|The =TEXT\(\) function in Excel changes with the locale\.<br /><br /><br /><br />Imagine you have a cell with the value "1\.23" and format the cell with a number format of "0\.00"\.<br />If you open the file with an English\-Localized Excel you will see "1\.23", but if you open the same file with a German\-Localized Excel, you will see "1,23" instead\. It happens automatically\.<br /><br /><br /><br />But if you have a formula '=&#8203;TEXT\(&#8203;1\.&#8203;23,&#8203;"0\.&#8203;00"&#8203;\)&#8203;' it will show correctly in an English\-Localized Excel, and as '123' in a German\-Localized one\. This is because the format string "0\.00" is not converted automatically to "0,00" which is what a German Excel would need\.<br />[...[more]](LocalizedTEXTFunction.md)|



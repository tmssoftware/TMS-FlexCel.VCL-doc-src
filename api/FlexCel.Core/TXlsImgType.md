---
uid: TXlsImgType
description: TXlsImgType
---

# TXlsImgType Enumeration

Possible image types on an excel sheet\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Emf|0|Enhanced Windows Metafile\. This is a Vectorial image format\.<br /><br />It is only rendered when using a GDI\+ graphics backend \(That is Windows\)\.<br />|
|Wmf|1|Windows Metafile\. This is a Vectorial image format\.<br /><br />It is only rendered when using a GDI\+ graphics backend \(That is Windows\)\.<br />|
|Jpeg|2|JPEG Image\. This is a lossy compressed bitmap, best suited for photos\.<br />|
|Png|3|Portable Network Graphics\. This is a losslessly compressed bitmap, best suited for text\.<br />|
|Bmp|4|Windows Bitmap\. As this is not compressed, don't use it except for really small images\.<br />|
|Pict|5|Macintosh PICT\. This won't be rendered by FlexCel, and you shouldn't add images in this format\.<br />This file format was used in the original macOS, and has been deprecated since OSX\.<br />|
|Tiff|6|Tiff Image: [http://partners.adobe.com/public/developer/tiff/index.html#spec](http://partners.adobe.com/public/developer/tiff/index.html#spec)  This is NOT supported in xls file format, only xlsx\.<br /><br />It is only rendered when using a GDI\+ graphics backend \(That Windows\)\.<br />|
|Gif|7|Gif Image\.<br />This is NOT supported in xls file format, only xlsx\. It is reasonably supported in graphics backends, but whenever possible you should prefer using PNGs\. Almost the only use case for gif images is for animated gifs\.<br />|
|Svg|8|SVG Image\. This is a vectorial vector, only supported in Excel 2019\+ or Excel 365\. As older Excels don't support SVG, Excel saves both a PNG image for them and an SVG image for the newer formats\. When adding an SVG with the API, you need to supply both the SVG and the backup PNG\. For more information see [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles)\.<br />|
|Unknown|9|Unsupported image format\.<br />|



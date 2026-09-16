---
uid: TUIImage
description: TUIImage
---

# TUIImage Class

A platform independent image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUIImage = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[ConvertTo256Colors](ConvertTo256Colors.md)|Converts the image to 256 indexed colors\.<br />|
|[ConvertToBiLevel](ConvertToBiLevel.md)|Converts the image to pure black and white, without diffusion\.<br />|
|[ConvertToBWDither](ConvertToBWDither.md)|Converts the image to pure black and white, using dithering\.<br />|
|[ConvertToGrayscale](ConvertToGrayscale.md)|Converts the image to shades of gray\.<br />|
|[CreateBitmap](CreateBitmap.md)|Creates a bitmap of the specified dimensions\.<br />|
|[FromFile](FromFile.md)|Creates an image from a file in the disk\.<br />|
|[FromStream](FromStream.md)|Creates an image from a stream\.<br />|
|[RasterMetafile](RasterMetafile.md)|Converts a vectorial metafile to a bitmap\.<br />|
|[Save](Save.md)|**Overloaded<br />**  [Save\(TStream, TXlsImgType\)](Save.md#tuiimagesavetstream-txlsimgtype)<br />  [Save\(string, TXlsImgType\)](Save.md#tuiimagesavestring-txlsimgtype)<br />|
|[SaveStart](SaveStart.md)|Starts saving a multi page image\.<br />|
|[SupportsMultiPage](SupportsMultiPage.md)|Returns true if the current platform supports multipage images\.<br />|
|[ToNativeImage](ToNativeImage.md)|**Overloaded<br />**  [ToNativeImage\(Pointer, Double\)](ToNativeImage.md#tuiimagetonativeimagepointer-double)<br />  [ToNativeImage\(Double, Double, Pointer, Double\)](ToNativeImage.md#tuiimagetonativeimagedouble-double-pointer-double)<br />|


## Properties

|Name|Description|
|---|---|
|[Height](Height.md)|Height of the image in device\-dependent pixels\.<br />|
|[HeightInPoints](HeightInPoints.md)|Height of the image in Points \(1/72 of an inch\)|
|[Is8bitGrayscale](Is8bitGrayscale.md)|Returns true if the image has 256 shades of gray\.<br />|
|[IsMetafile](IsMetafile.md)|Returns true if the file is a WMF or EMF file\.<br />|
|[RawFormat](RawFormat.md)|Format of the image\.<br />|
|[Width](Width.md)|Width of the image in device\-dependent pixels\.<br />|
|[WidthInPoints](WidthInPoints.md)|Width of the image in Points \(1/72 of an inch\)|



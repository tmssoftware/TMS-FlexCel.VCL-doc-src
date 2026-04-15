---
uid: TXlsFile.RenderObject
description: TXlsFile.RenderObject
---

# TXlsFile\.RenderObject Method

This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RenderObject(const objectIndex: Integer; const dpi: Double; shapeProperties: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; const aSmoothingMode: TSmoothingMode; const aInterpolationMode: TInterpolationMode; const antiAliased: Boolean; const returnImage: Boolean; const BackgroundColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const aPrintScale: Double; out origin: <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; out imageSizePixels: <a href="../../FlexCel.Core/TUISize/index.md">TUISize</a>): <a href="../../FlexCel.Core/TUIImage/index.md">TUIImage</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**dpi**|Double|Resolution of the image to create in dots per inch\. If creating the image for the screen, use 96 dpi\.|
||**shapeProperties**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**aSmoothingMode**|TSmoothingMode|Smoothing mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.SmoothingMode"|
|const|**aInterpolationMode**|TInterpolationMode|Interpolation mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.InterpolationMode"|
|const|**antiAliased**|Boolean|If true text will be antialiased when rendering for example a chart\.|
|const|**returnImage**|Boolean|If false, this method will return null\. Use it if you need to know the image dimensions, but do not care about the real image since it is faster and uses less resources\.|
|const|**BackgroundColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**aPrintScale**|Double||
|out|**origin**|[TUIPointF](../../FlexCel.Core/TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [TExcelFile.GetImageProperties\(Integer\)](../../FlexCel.Core/TExcelFile/GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\. You can get the image size in pixels just by looking at the image returned\.|
|out|**imageSizePixels**|[TUISize](../../FlexCel.Core/TUISize/index.md)|Size of the returned image in pixels\. You only need to use this if returnImage is false, since the returned bitmap will be null\. Otherwise, you can just read the bitmap size\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TXlsFile](../TXlsFile/index.md)


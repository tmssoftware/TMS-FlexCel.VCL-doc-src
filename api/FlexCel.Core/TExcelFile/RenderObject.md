---
uid: TExcelFile.RenderObject
description: TExcelFile.RenderObject
---

# TExcelFile\.RenderObject Method

## Overloads

* [TExcelFile\.RenderObject\(Integer\)](#texcelfilerenderobjectinteger)
* [TExcelFile\.RenderObject\(Integer, string\)](#texcelfilerenderobjectinteger-string)
* [TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIPointF, TUIRectangle, TUISize\)](#texcelfilerenderobjectinteger-double-ishapeproperties-tsmoothingmode-tinterpolationmode-boolean-boolean-tuipointf-tuirectangle-tuisize)
* [TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIColor, TUIPointF, TUIRectangle, TUISize\)](#texcelfilerenderobjectinteger-double-ishapeproperties-tsmoothingmode-tinterpolationmode-boolean-boolean-tuicolor-tuipointf-tuirectangle-tuisize)
* [TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIColor, Double, TUIPointF, TUIRectangle, TUISize\)](#texcelfilerenderobjectinteger-double-ishapeproperties-tsmoothingmode-tinterpolationmode-boolean-boolean-tuicolor-double-tuipointf-tuirectangle-tuisize)

# TExcelFile\.RenderObject\(Integer\)
This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.

Background of the image will be transparent\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObject(const objectIndex: Integer): <a href="../TUIImage/index.md">TUIImage</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObject\(Integer, string\)
This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.

Background of the image will be transparent\.


## Remarks

This method uses [DpiForImages](DpiForImages.md) to determine the dpi of the returned image, and sets all  other values in other overload of RenderObject to their defaults\. If you need more control over the parameters passed to RenderObject, you can use any overload which takes a [IShapeProperties](../IShapeProperties/index.md) parameter, and pass a shapeProperties from the object you want to render\. While those overloads take an objectIndex and no objectPath, what is used for rendering is the shapeProperties\. The objectIndex is only used to determine the position of the object in the z axis\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObject(const objectIndex: Integer; const objectPath: string): <a href="../TUIImage/index.md">TUIImage</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**objectPath**|string|Path to the object to render\. Look at [GetObjectProperties\(Integer, string, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-string-boolean)  for a description of the possible values\.|


## Returns

Might return null if the image is not visible\.

## Examples

To save the image of a chart named "my\_pie\_chart" to disk as a png image, you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  img: TUIImage;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  img := xls.RenderObject(-</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'@my_pie_chart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    img.Save(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfilename.png'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsImgType.Png);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    img.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIPointF, TUIRectangle, TUISize\)
This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObject(const objectIndex: Integer; const dpi: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const aSmoothingMode: TSmoothingMode; const aInterpolationMode: TInterpolationMode; const antiAliased: Boolean; const returnImage: Boolean; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>; out imageSizePixels: <a href="../TUISize/index.md">TUISize</a>): <a href="../TUIImage/index.md">TUIImage</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**dpi**|Double|Resolution of the image to create in dots per inch\. If creating the image for a low\-resolution screen, use 96 dpi\.|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**aSmoothingMode**|TSmoothingMode|Smoothing mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.SmoothingMode"|
|const|**aInterpolationMode**|TInterpolationMode|Interpolation mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.InterpolationMode"|
|const|**antiAliased**|Boolean|If true text will be antialiased when rendering for example a chart\.|
|const|**returnImage**|Boolean|If false, this method will return null\. Use it if you need to know the image dimensions, but do not care about the real image since it is faster and uses less resources\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties, if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\. You can get the image size in pixels just by looking at the image returned\.|
|out|**imageSizePixels**|[TUISize](../TUISize/index.md)|Size of the returned image in pixels\. You only need to use this if returnImage is false, since the returned bitmap will be null\. Otherwise, you can just read the bitmap size\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIColor, TUIPointF, TUIRectangle, TUISize\)
This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObject(const objectIndex: Integer; const dpi: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const aSmoothingMode: TSmoothingMode; const aInterpolationMode: TInterpolationMode; const antiAliased: Boolean; const returnImage: Boolean; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>; out imageSizePixels: <a href="../TUISize/index.md">TUISize</a>): <a href="../TUIImage/index.md">TUIImage</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**dpi**|Double|Resolution of the image to create in dots per inch\. If creating the image for the screen, use 96 dpi\.|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**aSmoothingMode**|TSmoothingMode|Smoothing mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.SmoothingMode"|
|const|**aInterpolationMode**|TInterpolationMode|Interpolation mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.InterpolationMode"|
|const|**antiAliased**|Boolean|If true text will be antialiased when rendering for example a chart\.|
|const|**returnImage**|Boolean|If false, this method will return null\. Use it if you need to know the image dimensions, but do not care about the real image since it is faster and uses less resources\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties, if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\. You can get the image size in pixels just by looking at the image returned\.|
|out|**imageSizePixels**|[TUISize](../TUISize/index.md)|Size of the returned image in pixels\. You only need to use this if returnImage is false, since the returned bitmap will be null\. Otherwise, you can just read the bitmap size\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObject\(Integer, Double, IShapeProperties, TSmoothingMode, TInterpolationMode, Boolean, Boolean, TUIColor, Double, TUIPointF, TUIRectangle, TUISize\)
This method renders any object \(chart, image, autoshape, etc\) into an image, and returns it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObject(const objectIndex: Integer; const dpi: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const aSmoothingMode: TSmoothingMode; const aInterpolationMode: TInterpolationMode; const antiAliased: Boolean; const returnImage: Boolean; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const aPageScale: Double; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>; out imageSizePixels: <a href="../TUISize/index.md">TUISize</a>): <a href="../TUIImage/index.md">TUIImage</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**dpi**|Double|Resolution of the image to create in dots per inch\. If creating the image for the screen, use 96 dpi\.|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**aSmoothingMode**|TSmoothingMode|Smoothing mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.SmoothingMode"|
|const|**aInterpolationMode**|TInterpolationMode|Interpolation mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.InterpolationMode"|
|const|**antiAliased**|Boolean|If true text will be antialiased when rendering for example a chart\.|
|const|**returnImage**|Boolean|If false, this method will return null\. Use it if you need to know the image dimensions, but do not care about the real image since it is faster and uses less resources\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\. You can get the image size in pixels just by looking at the image returned\.|
|out|**imageSizePixels**|[TUISize](../TUISize/index.md)|Size of the returned image in pixels\. You only need to use this if returnImage is false, since the returned bitmap will be null\. Otherwise, you can just read the bitmap size\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)


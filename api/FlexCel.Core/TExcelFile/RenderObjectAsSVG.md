---
uid: TExcelFile.RenderObjectAsSVG
description: TExcelFile.RenderObjectAsSVG
---

# TExcelFile\.RenderObjectAsSVG Method

## Overloads

* [TExcelFile\.RenderObjectAsSVG\(Integer, string, string, TEncoding\)](#texcelfilerenderobjectassvginteger-string-string-tencoding)
* [TExcelFile\.RenderObjectAsSVG\(TStream, Integer, string, string, TEncoding\)](#texcelfilerenderobjectassvgtstream-integer-string-string-tencoding)
* [TExcelFile\.RenderObjectAsSVG\(Integer, string, string, string, TEncoding\)](#texcelfilerenderobjectassvginteger-string-string-string-tencoding)
* [TExcelFile\.RenderObjectAsSVG\(TStream, Integer, string, string, string, TEncoding\)](#texcelfilerenderobjectassvgtstream-integer-string-string-string-tencoding)
* [TExcelFile\.RenderObjectAsSVG\(Integer, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvginteger-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-tuipointf-tuirectangle)
* [TExcelFile\.RenderObjectAsSVG\(TStream, Integer, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvgtstream-integer-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-tuipointf-tuirectangle)
* [TExcelFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvginteger-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-tuipointf-tuirectangle)
* [TExcelFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvgtstream-integer-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-tuipointf-tuirectangle)
* [TExcelFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvginteger-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-boolean-tuipointf-tuirectangle)
* [TExcelFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)](#texcelfilerenderobjectassvgtstream-integer-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-boolean-tuipointf-tuirectangle)

# TExcelFile\.RenderObjectAsSVG\(Integer, string, string, TEncoding\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const objectIndex: Integer; const title: string; const description: string; const encoding: TEncoding): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if ExportType is all\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the ExportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(TStream, Integer, string, string, TEncoding\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; const title: string; const description: string; const encoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the file will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(Integer, string, string, string, TEncoding\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Remarks

This method sets some values in other overloads of RenderObjectasSVG to their defaults\. If you need more control over the parameters passed to RenderObjectAsSVG, you can use any overload which takes a [IShapeProperties](../IShapeProperties/index.md) parameter, and pass a shapeProperties from the object you want to render\. While those overloads take an objectIndex and no objectPath, what is used for rendering is the shapeProperties\. The objectIndex is only used to determine the position of the object in the z axis\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const objectIndex: Integer; const objectPath: string; const title: string; const description: string; const encoding: TEncoding): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**objectPath**|string|Path to the object ot render\. Look at [GetObjectProperties\(Integer, string, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-string-boolean)  for a description of the possible values\.|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if ExportType is all\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the ExportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|


## Returns

Might return null if the image is not visible\.

## Examples

To save the image of a chart named "my\_pie\_chart" to disk as an SVG image, you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  svg: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  svg := xls.RenderObjectAsSVG(-</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'@my_pie_chart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is a chart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This chart was rendered with RenderObjectAsSVG'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TEncoding.UTF8);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TFile.WriteAllText(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfilename.svg'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, svg);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(TStream, Integer, string, string, string, TEncoding\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Remarks

This method sets some values in other overloads of RenderObjectasSVG to their defaults\. If you need more control over the parameters passed to RenderObjectAsSVG, you can use any overload which takes a [IShapeProperties](../IShapeProperties/index.md) parameter, and pass a shapeProperties from the object you want to render\. While those overloads take an objectIndex and no objectPath, what is used for rendering is the shapeProperties\. The objectIndex is only used to determine the position of the object in the z axis\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; const objectPath: string; const title: string; const description: string; const encoding: TEncoding); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the file will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**objectPath**|string|Path to the object to render\. Look at [GetObjectProperties\(Integer, string, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-string-boolean)  for a description of the possible values\.|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|


## Examples

To save the image of a chart named "my\_pie\_chart" to disk as an SVG image, you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SvgStream: TFileStream;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SvgStream := TFileStream.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfilename.svg'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, fmCreate);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.RenderObjectAsSVG(SvgStream, -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'@my_pie_chart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is a chart'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This chart was rendered with RenderObjectAsSVG'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TEncoding.UTF8);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    SvgStream.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(Integer, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const objectIndex: Integer; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if exportType is All\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the exportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(TStream, Integer, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the data will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if exportType is All\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the exportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, TUIPointF, TUIRectangle\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the data will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; const rasterizeSVGImages: Boolean; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>): string; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if exportType is All\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the exportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|
|const|**rasterizeSVGImages**|Boolean|If true, FlexCel will rasterize all SVG images in the Excel file to png before exporting them\.<br />See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../TUIColor/index.md">TUIColor</a>; const exportType: <a href="../TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; const rasterizeSVGImages: Boolean; out origin: <a href="../TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../TUIRectangle/index.md">TUIRectangle</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the data will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|
|const|**rasterizeSVGImages**|Boolean|If true, FlexCel will rasterize all SVG images in the Excel file to png before exporting them\.<br />See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.|
|out|**origin**|[TUIPointF](../TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [GetImageProperties\(Integer\)](GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


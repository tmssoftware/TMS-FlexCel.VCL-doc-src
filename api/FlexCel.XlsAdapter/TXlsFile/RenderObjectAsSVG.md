---
uid: TXlsFile.RenderObjectAsSVG
description: TXlsFile.RenderObjectAsSVG
---

# TXlsFile\.RenderObjectAsSVG Method

## Overloads

* [TXlsFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)](#txlsfilerenderobjectassvginteger-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-boolean-tuipointf-tuirectangle)
* [TXlsFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)](#txlsfilerenderobjectassvgtstream-integer-double-ishapeproperties-tuicolor-tsvgexporttype-string-string-string-tarraytsvgattribute-tencoding-boolean-tuipointf-tuirectangle)

# TXlsFile\.RenderObjectAsSVG\(Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)
This method renders any object \(chart, image, autoshape, etc\) into an SVG image, and returns the XML for the image\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RenderObjectAsSVG(const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const exportType: <a href="../../FlexCel.Core/TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../../FlexCel.Core/TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; const rasterizeSVGImages: Boolean; out origin: <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>): string; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../../FlexCel.Core/TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../../FlexCel.Core/TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be declared for the xml file if exportType is All\.<br />Note that the result string will always be UTF16 encoded, but if you want to save it to an UTF8 file, you will have to set encoding = utf8\. Also note that this parameter is only used if the exportType parameter is All\.<br />It only affects the xml declaration\.<br />If null, utf\-8 will be used\.|
|const|**rasterizeSVGImages**|Boolean|If true, FlexCel will rasterize all SVG images in the Excel file to png before exporting them\.<br />See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.|
|out|**origin**|[TUIPointF](../../FlexCel.Core/TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [TExcelFile.GetImageProperties\(Integer\)](../../FlexCel.Core/TExcelFile/GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## Returns

Might return null if the image is not visible\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.RenderObjectAsSVG\(TStream, Integer, Double, IShapeProperties, TUIColor, TSVGExportType, string, string, string, TArray\<TSVGAttribute>, TEncoding, Boolean, TUIPointF, TUIRectangle\)
This method saves any object \(chart, image, autoshape, etc\) into an SVG image inside a stream\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.RenderObjectAsSVG(const resultStream: TStream; const objectIndex: Integer; const aPageScale: Double; shapeProperties: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; const BackgroundColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const exportType: <a href="../../FlexCel.Core/TSVGExportType.md">TSVGExportType</a>; const idPrefix: string; const title: string; const description: string; const extraSVGAttributes: TArray&lt;<a href="../../FlexCel.Core/TSVGAttribute/index.md">TSVGAttribute</a>&gt;; const encoding: TEncoding; const rasterizeSVGImages: Boolean; out origin: <a href="../../FlexCel.Core/TUIPointF/index.md">TUIPointF</a>; out imageDimensions: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**resultStream**|TStream|Stream where the data will be saved\.|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.<br />**Note:** This object index is not used to get the object to render, which is given by the shapeProperties parameter\. The object index is only used to determine the z\-order of the object\. If shapeProperties refers to a grouped object, pass the object index of the main group here\.|
|const|**aPageScale**|Double|Page scale\. Use 1 for 100%%|
||**shapeProperties**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|Properties of the shape you are about to render\. You can get them by calling [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)\.|
|const|**BackgroundColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Color for the background of the image\. For a transparent background, use TUIColor\.Empty\.|
|const|**exportType**|[TSVGExportType](../../FlexCel.Core/TSVGExportType.md)|How much of the SVG will be exported\.|
|const|**idPrefix**|string|Prefix to be used in all definitions inside the svg file\. For normal SVG files you can leave this null, but if you are embedding the files inside an html file, you need to ensure every image has unique identifiers\.<br />All SVG identifiers from different images inside an html file must be unique\.<br />|
|const|**title**|string|Title for the image\. It will be saved inside the SVG file\.|
|const|**description**|string|Description for the image\. It will be saved inside the SVG file\.|
|const|**extraSVGAttributes**|TArray\<[TSVGAttribute](../../FlexCel.Core/TSVGAttribute/index.md)>|Extra attributes to be added to the svg tag\.|
|const|**encoding**|TEncoding|Encoding that will be used for the xml\.<br />If null, utf\-8 will be used\.|
|const|**rasterizeSVGImages**|Boolean|If true, FlexCel will rasterize all SVG images in the Excel file to png before exporting them\.<br />See [S V G Files Inside Xlsx Files](xref:SVGFilesInsideXlsxFiles) for more information\.|
|out|**origin**|[TUIPointF](../../FlexCel.Core/TUIPointF/index.md)|Top\-left coordinates of the image in points\. While this is normally the same as the image coordinates you get in the properties,  if there is a shadow to the right or to the top it might change\. Use it to properly position the image where you want it\.|
|out|**imageDimensions**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Returns the image dimension of the rendered object in points\. Note that this can be different from the image size reported by  [TExcelFile.GetImageProperties\(Integer\)](../../FlexCel.Core/TExcelFile/GetImageProperties.md#texcelfilegetimagepropertiesinteger) because shadows or rotation of the image\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.RenderCells
description: TXlsFile.RenderCells
---

# TXlsFile\.RenderCells Method

This method renders a range of cells into an image, and returns it\.

No objects will be drawn on the cells, you can use [TExcelFile.RenderObject\(Integer\)](../../FlexCel.Core/TExcelFile/RenderObject.md#texcelfilerenderobjectinteger) to draw those\.
**Important note:** By default this method will only render the text inside the cell, not the borders or cell fills or anything else\. If you want to  export an xls file to images, you need to set the parameter "exportObjects" to true, or use [TFlexCelImgExport](../../FlexCel.Render/TFlexCelImgExport/index.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RenderCells(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer; const drawBackground: Boolean; const dpi: Double; const aSmoothingMode: TSmoothingMode; const aInterpolationMode: TInterpolationMode; const antiAliased: Boolean; const aPrintScale: Double; const forceBackgroundTransparent: Boolean; const exportObjects: Boolean): <a href="../../FlexCel.Core/TUIImage/index.md">TUIImage</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Index of the first row to render\. \(1 based\)\.|
|const|**col1**|Integer|Index of the first column to render \(1 based\)\.|
|const|**row2**|Integer|Index of the last row to render\. \(1 based\)\.|
|const|**col2**|Integer|Index of the last column to render \(1 based\)\.|
|const|**drawBackground**|Boolean|If true, the image will have a solid background with the color of the cells\. If false, the image will have a transparent background\.|
|const|**dpi**|Double|Resolution of the image to create in dots per inch\. If creating the image for the screen, use 96 dpi\.|
|const|**aSmoothingMode**|TSmoothingMode|Smoothing mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.SmoothingMode"|
|const|**aInterpolationMode**|TInterpolationMode|Interpolation mode used to render the object\. For more information, see "System\.Drawing\.Drawing2D\.InterpolationMode"|
|const|**antiAliased**|Boolean|If true text will be antialiased when rendering\.|
|const|**aPrintScale**|Double||
|const|**forceBackgroundTransparent**|Boolean|If true the background of the image will be transparent for the cells that don't have fill, even if drawBackground is true\.|
|const|**exportObjects**|Boolean|If false, only the cells themselves will be rendered, with no borders, images, etc\. If true, objects will be rendered too\.|


## Returns

An image with the rendered cells\.

## See also

* [TXlsFile](../TXlsFile/index.md)


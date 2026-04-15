---
uid: TFlexCelImgExport.SaveAsImage
description: TFlexCelImgExport.SaveAsImage
---

# TFlexCelImgExport\.SaveAsImage Method

## Overloads

* [TFlexCelImgExport\.SaveAsImage\(string, TImageExportType, TImageColorDepth\)](#tflexcelimgexportsaveasimagestring-timageexporttype-timagecolordepth)
* [TFlexCelImgExport\.SaveAsImage\(TStream, TImageExportType, TImageColorDepth\)](#tflexcelimgexportsaveasimagetstream-timageexporttype-timagecolordepth)

# TFlexCelImgExport\.SaveAsImage\(string, TImageExportType, TImageColorDepth\)
Saves the current Excel file as an image file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelImgExport/index.md">TFlexCelImgExport</a>.SaveAsImage(const fileName: string; const exportFormat: <a href="../../FlexCel.Core/TImageExportType.md">TImageExportType</a>; const ColorDepth: <a href="../../FlexCel.Core/TImageColorDepth.md">TImageColorDepth</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File where the image will be saved\.|
|const|**exportFormat**|[TImageExportType](../../FlexCel.Core/TImageExportType.md)|Image format\.|
|const|**ColorDepth**|[TImageColorDepth](../../FlexCel.Core/TImageColorDepth.md)|Color depth for the image, if applicable\. Some formats \(like fax, that is monochrome\) do not allow different color depths\.|


## See also

* [TFlexCelImgExport](../TFlexCelImgExport/index.md)

# TFlexCelImgExport\.SaveAsImage\(TStream, TImageExportType, TImageColorDepth\)
Saves the current Excel file on an image stream\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelImgExport/index.md">TFlexCelImgExport</a>.SaveAsImage(const fileStream: TStream; const exportFormat: <a href="../../FlexCel.Core/TImageExportType.md">TImageExportType</a>; const ColorDepth: <a href="../../FlexCel.Core/TImageColorDepth.md">TImageColorDepth</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileStream**|TStream|Stream where the image will be saved\.|
|const|**exportFormat**|[TImageExportType](../../FlexCel.Core/TImageExportType.md)|Image format\.|
|const|**ColorDepth**|[TImageColorDepth](../../FlexCel.Core/TImageColorDepth.md)|Color depth for the image, if applicable\. Some formats \(like fax, that is monochrome\) do not allow different color depots\.|


## See also

* [TFlexCelImgExport](../TFlexCelImgExport/index.md)


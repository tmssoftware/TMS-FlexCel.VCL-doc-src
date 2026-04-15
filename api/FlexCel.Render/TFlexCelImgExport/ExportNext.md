---
uid: TFlexCelImgExport.ExportNext
description: TFlexCelImgExport.ExportNext
---

# TFlexCelImgExport\.ExportNext Method

## Overloads

* [TFlexCelImgExport\.ExportNext\(TUIGraphics, IImgExportInfo\)](#tflexcelimgexportexportnexttuigraphics-iimgexportinfo)
* [TFlexCelImgExport\.ExportNext\(TStream, TImageColorDepth, TXlsImgType, IImgExportInfo\)](#tflexcelimgexportexportnexttstream-timagecolordepth-txlsimgtype-iimgexportinfo)
* [TFlexCelImgExport\.ExportNext\(string, TImageColorDepth, TXlsImgType, IImgExportInfo\)](#tflexcelimgexportexportnextstring-timagecolordepth-txlsimgtype-iimgexportinfo)

# TFlexCelImgExport\.ExportNext\(TUIGraphics, IImgExportInfo\)
Exports the associated xls workbook to a graphics stream\. You need to provide a  Graphics object with the correct dimensions\. \(To get the needed dimensions, use [GetRealPageSize](GetRealPageSize.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelImgExport/index.md">TFlexCelImgExport</a>.ExportNext(imgData: <a href="../../FlexCel.Core/TUIGraphics/index.md">TUIGraphics</a>; var exportInfo: <a href="../IImgExportInfo/index.md">IImgExportInfo</a>): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**imgData**|[TUIGraphics](../../FlexCel.Core/TUIGraphics/index.md)|Graphics where the image will be stored\. Set it to null to skip the page\.|
|var|**exportInfo**|[IImgExportInfo](../IImgExportInfo/index.md)|Information needed to export, cached for speed\. The first time you call this method \(or when you change xls\.ActiveSheet\), make exportInfo=null|


## See also

* [TFlexCelImgExport](../TFlexCelImgExport/index.md)

# TFlexCelImgExport\.ExportNext\(TStream, TImageColorDepth, TXlsImgType, IImgExportInfo\)
Exports the associated xls workbook to a stream\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelImgExport/index.md">TFlexCelImgExport</a>.ExportNext(const imgStream: TStream; const colorDepth: <a href="../../FlexCel.Core/TImageColorDepth.md">TImageColorDepth</a>; const imgFormat: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; var exportInfo: <a href="../IImgExportInfo/index.md">IImgExportInfo</a>): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imgStream**|TStream|Stream where the image will be exported\.|
|const|**colorDepth**|[TImageColorDepth](../../FlexCel.Core/TImageColorDepth.md)|Number of colors for the image\.|
|const|**imgFormat**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Format for the saved image|
|var|**exportInfo**|[IImgExportInfo](../IImgExportInfo/index.md)|Information needed to export, cached for speed\. The first time you call this method \(or when you change xls\.ActiveSheet\), make exportInfo=null|


## See also

* [TFlexCelImgExport](../TFlexCelImgExport/index.md)

# TFlexCelImgExport\.ExportNext\(string, TImageColorDepth, TXlsImgType, IImgExportInfo\)
Exports the associated xls workbook to a file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelImgExport/index.md">TFlexCelImgExport</a>.ExportNext(const fileName: string; const colorDepth: <a href="../../FlexCel.Core/TImageColorDepth.md">TImageColorDepth</a>; const imgFormat: <a href="../../FlexCel.Core/TXlsImgType.md">TXlsImgType</a>; var exportInfo: <a href="../IImgExportInfo/index.md">IImgExportInfo</a>): Boolean; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to export\.|
|const|**colorDepth**|[TImageColorDepth](../../FlexCel.Core/TImageColorDepth.md)|Number of colors for the image\.|
|const|**imgFormat**|[TXlsImgType](../../FlexCel.Core/TXlsImgType.md)|Format for the saved image|
|var|**exportInfo**|[IImgExportInfo](../IImgExportInfo/index.md)|Information needed to export, cached for speed\. The first time you call this method \(or when you change xls\.ActiveSheet\), make exportInfo=null|


## See also

* [TFlexCelImgExport](../TFlexCelImgExport/index.md)


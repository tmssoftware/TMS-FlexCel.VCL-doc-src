---
uid: TFlexCelHtmlExport.Export
description: TFlexCelHtmlExport.Export
---

# TFlexCelHtmlExport\.Export Method

## Overloads

* [TFlexCelHtmlExport\.Export\(string, string\)](#tflexcelhtmlexportexportstring-string)
* [TFlexCelHtmlExport\.Export\(TFlexCelWriter, string, ICssInformation\)](#tflexcelhtmlexportexporttflexcelwriter-string-icssinformation)
* [TFlexCelHtmlExport\.Export\(string, string, ICssInformation\)](#tflexcelhtmlexportexportstring-string-icssinformation)
* [TFlexCelHtmlExport\.Export\(string, string, string\)](#tflexcelhtmlexportexportstring-string-string)

# TFlexCelHtmlExport\.Export\(string, string\)
Exports the active sheet of the the associated xls workbook to a file\. CSS will be saved internally in the file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.Export(const htmlFileName: string; const relativeImagePath: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**htmlFileName**|string|File name of the html file to be created\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the main file\.<br />If for example htmlFileName is "c:\\reports\\html\\index\.htm" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html file\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

# TFlexCelHtmlExport\.Export\(TFlexCelWriter, string, ICssInformation\)
Exports the active sheet of the associated xls workbook to a TextWriter\. Note that you need to supply the stream for saving the images  in the [GetImageInformation](GetImageInformation.md) event \(if you want to save the images\)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.Export(const html: <a href="../../FlexCel.Core/TFlexCelWriter/index.md">TFlexCelWriter</a>; const fileName: string; css: <a href="../ICssInformation/index.md">ICssInformation</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**html**|[TFlexCelWriter](../../FlexCel.Core/TFlexCelWriter/index.md)|TextWriter where the result will be written\.|
|const|**fileName**|string|FileName used to generate the supporting files\. If you leave it null, no images will be saved as there will not be filename for them\.|
||**css**|[ICssInformation](../ICssInformation/index.md)|Use this parameter to store all CSS information in an external file\. Set it to null if you want to store the CSS inside the HTML file\. If you want to share the CSS between multiple files, make sure you pass the same css parameter to all Export calls\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

# TFlexCelHtmlExport\.Export\(string, string, ICssInformation\)
Exports the active sheet of the the associated xls workbook to a file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.Export(const htmlFileName: string; const relativeImagePath: string; css: <a href="../ICssInformation/index.md">ICssInformation</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**htmlFileName**|string|File name of the html file to be created\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the main file\.<br />If for example htmlFileName is "c:\\reports\\html\\index\.htm" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html file\.|
||**css**|[ICssInformation](../ICssInformation/index.md)|Use this parameter to store all CSS information in an external file\. Set it to null if you want to store the CSS inside the HTML file\. If you want to share the CSS between multiple files, make sure you pass the same css parameter to all Export calls\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

# TFlexCelHtmlExport\.Export\(string, string, string\)
Exports the active sheet of the the associated xls workbook to a file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.Export(const htmlFileName: string; const relativeImagePath: string; const relativeCssFileName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**htmlFileName**|string|File name of the html file to be created\.|
|const|**relativeImagePath**|string|Folder where images will be stored, relative to the main file\.<br />If for example htmlFileName is "c:\\reports\\html\\index\.htm" and relativeImagePath is "images", images will be saved in folder "c:\\reports\\html\\images"\. If this parameter is null or empty, images will be saved in the same folder as the html file\.|
|const|**relativeCssFileName**|string|Name for the Css file, with a path relative to the htmlPath\.<br />If you set it to null, no css file created and the css will be stored inside each HTML file\.<br />If for example htmlpath is "c:\\reports" and relativeCssFileName is "css\\data\.css" the css file will be saved in "c:\\reports\\css\\data\.css"|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)


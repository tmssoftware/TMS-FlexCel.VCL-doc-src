---
uid: TFlexCelHtmlExport.PartialExportAdd
description: TFlexCelHtmlExport.PartialExportAdd
---

# TFlexCelHtmlExport\.PartialExportAdd Method

## Overloads

* [TFlexCelHtmlExport\.PartialExportAdd\(TPartialExportState, string, string\)](#tflexcelhtmlexportpartialexportaddtpartialexportstate-string-string)
* [TFlexCelHtmlExport\.PartialExportAdd\(TPartialExportState, string, string, Boolean\)](#tflexcelhtmlexportpartialexportaddtpartialexportstate-string-string-boolean)

# TFlexCelHtmlExport\.PartialExportAdd\(TPartialExportState, string, string\)
This method is designed to export a part of the HTML inside another HTML file\.
You should call this method once for every file you wish to export,  in order to let FlexCel consolidate the necessary CSS classes and information into the partialExportState parameter\.
Once you have "filled" the partialExportState object with all the information on files you wish to export, you can call the methods in partialExportState to write the CSS or body parts of the HTML file\.


Note that this overload version will automatically save the images to disk when needed\. If for any reason you do not want to save the images, use the overload with SaveImagesToDisk parameter\.



## Remarks

This method does \*not\* clear the generated files array, so you have more control over it\. If you want to use it, you need to call the clear method yourself before the first PartialExportAdd\.

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.PartialExportAdd(const partialExportState: <a href="../TPartialExportState/index.md">TPartialExportState</a>; const htmlFileName: string; const relativeImagePath: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**partialExportState**|[TPartialExportState](../TPartialExportState/index.md)|Object where we will collect all the css and needed information on the files being exported\. Call this method once for every sheet you want to export, using the same partialExportState parameter\.|
|const|**htmlFileName**|string|Name of the stored html file\. This affects the path where images will be saved, and also the way images will be named\.|
|const|**relativeImagePath**|string|Path relative to the path of htmlFileName, where images will be stored\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)

# TFlexCelHtmlExport\.PartialExportAdd\(TPartialExportState, string, string, Boolean\)
This method is designed to export a part of the HTML inside other HTML file\.
You should call this method once for every file you wish to export,  in order to let FlexCel consolidate the needed CSS classes and information into the partialExportState parameter\.
Once you have "filled" the partialExportState object with all the information on files you wish to export, you can call the methods in partialExportState to write the CSS or body parts of the HTML file\.


## Remarks

This method does \*not\* clear the generated files array, so you have more control over it\. If you want to use it, you need to call the clear method yourself before the first PartialExportAdd\.

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelHtmlExport/index.md">TFlexCelHtmlExport</a>.PartialExportAdd(const partialExportState: <a href="../TPartialExportState/index.md">TPartialExportState</a>; const htmlFileName: string; const relativeImagePath: string; const SaveImagesToDisk: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**partialExportState**|[TPartialExportState](../TPartialExportState/index.md)|Object where we will collect all the css and needed information on the files being exported\. Call this method once for every sheet you want to export, using the same partialExportState parameter\.|
|const|**htmlFileName**|string|Name of the stored html file\. This affects the path where images will be saved, and also the way images will be named\.|
|const|**relativeImagePath**|string|Path relative to the path of htmlFileName, where images will be stored\.|
|const|**SaveImagesToDisk**|Boolean|When true, any image found in the file will be saved to disk \(to relative imagepath\) as the file is added\.<br />If false, the links for the image will be written but no image will be saved to disk, you have to do this yourself\. Note that when  saving MHTML files this parameter doesn't matter, since images will not be saved to disk anyway\.|


## See also

* [TFlexCelHtmlExport](../TFlexCelHtmlExport/index.md)


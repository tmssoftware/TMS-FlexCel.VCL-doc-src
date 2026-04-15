---
uid: TExcelFile.HasImageAlternate
description: TExcelFile.HasImageAlternate
---

# TExcelFile\.HasImageAlternate Method

Returns true if the image has an alternate representation\. This currently happens only with SVG images, which have a PNG base and an SVG alternate\. If the image has an alternate, you can get the data with [GetImageAlternate](GetImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.HasImageAlternate(const imageIndex: Integer; const objectPath: string; const usesObjectIndex: Boolean): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image\. \(1 based\)|
|const|**objectPath**|string|Object path to the image when it is a grouped image\. For toplevel images you can use String\.Empty\.<br />In other case, you need to use the value returned by [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />**Important:** ObjectPath is ignored if **usesObjectIndex** is false\.<br /><br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"<br />You might also use the name of the image as object path, like in xls\.GetImage\(\-1, "@myimage", ref imageType, ImageStream, true\)|
|const|**usesObjectIndex**|Boolean|If false then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


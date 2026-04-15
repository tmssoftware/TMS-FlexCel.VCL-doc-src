---
uid: IExcelChart.GetImageProperties
description: IExcelChart.GetImageProperties
---

# IExcelChart\.GetImageProperties Method

Returns image position and size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IExcelChart/index.md">IExcelChart</a>.GetImageProperties(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string): <a href="../IImageProperties/index.md">IImageProperties</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute" \(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

Image position and size\.

## See also

* [IExcelChart](../IExcelChart/index.md)


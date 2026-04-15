---
uid: TExcelFile.GetImageProperties
description: TExcelFile.GetImageProperties
---

# TExcelFile\.GetImageProperties Method

## Overloads

* [TExcelFile\.GetImageProperties\(Integer\)](#texcelfilegetimagepropertiesinteger)
* [TExcelFile\.GetImageProperties\(Integer, Boolean, string\)](#texcelfilegetimagepropertiesinteger-boolean-string)

# TExcelFile\.GetImageProperties\(Integer\)
Returns image position and size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetImageProperties(const imageIndex: Integer): <a href="../IImageProperties/index.md">IImageProperties</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|


## Returns

Image position and size\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetImageProperties\(Integer, Boolean, string\)
Returns image position and size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetImageProperties(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string): <a href="../IImageProperties/index.md">IImageProperties</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

Image position and size\.

## See also

* [TExcelFile](../TExcelFile/index.md)


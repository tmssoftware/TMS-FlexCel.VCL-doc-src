---
uid: TExcelFile.GetImageName
description: TExcelFile.GetImageName
---

# TExcelFile\.GetImageName Method

## Overloads

* [TExcelFile\.GetImageName\(Integer\)](#texcelfilegetimagenameinteger)
* [TExcelFile\.GetImageName\(Integer, Boolean, string\)](#texcelfilegetimagenameinteger-boolean-string)

# TExcelFile\.GetImageName\(Integer\)
Returns the image name at position imageIndex\.


## Remarks

Normally image names are automatically assigned by Excel, and are on the form "picture1", "picture2", etc\. But you can name an image on Excel by selecting and then typing its name on the name combo box\. \(the combobox at the upper left corner on Excel\)\. After that, you can use its name to identify it here\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetImageName(const imageIndex: Integer): string; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|


## Returns

Image name\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetImageName\(Integer, Boolean, string\)
Returns the image name at position imageIndex\.


## Remarks

Normally image names are automatically assigned by Excel, and are on the form "picture1", "picture2", etc\. But you can name an image on Excel by selecting and then typing its name on the name combo box\. \(the combobox at the upper left corner on Excel\)\. After that, you can use its name to identify it here\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetImageName(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string): string; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

Image name\.

## See also

* [TExcelFile](../TExcelFile/index.md)


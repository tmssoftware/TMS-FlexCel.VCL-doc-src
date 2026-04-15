---
uid: TExcelFile.DeleteImage
description: TExcelFile.DeleteImage
---

# TExcelFile\.DeleteImage Method

## Overloads

* [TExcelFile\.DeleteImage\(Integer\)](#texcelfiledeleteimageinteger)
* [TExcelFile\.DeleteImage\(Integer, Boolean, string\)](#texcelfiledeleteimageinteger-boolean-string)

# TExcelFile\.DeleteImage\(Integer\)
Deletes the image at position imageIndex\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteImage(const imageIndex: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image to delete\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.DeleteImage\(Integer, Boolean, string\)
Deletes the image at position imageIndex\. Note that if the image is grouped, this will remove the full group\.
To remove a particular image inside a group, use [DeleteObject\(Integer, string\)](DeleteObject.md#texcelfiledeleteobjectinteger-string)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteImage(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image to delete\. \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)


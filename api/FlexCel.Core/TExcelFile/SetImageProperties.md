---
uid: TExcelFile.SetImageProperties
description: TExcelFile.SetImageProperties
---

# TExcelFile\.SetImageProperties Method

## Overloads

* [TExcelFile\.SetImageProperties\(Integer, IImageProperties\)](#texcelfilesetimagepropertiesinteger-iimageproperties)
* [TExcelFile\.SetImageProperties\(Integer, IImageProperties, Boolean, string\)](#texcelfilesetimagepropertiesinteger-iimageproperties-boolean-string)

# TExcelFile\.SetImageProperties\(Integer, IImageProperties\)
Sets the image properties of an existing image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImageProperties(const imageIndex: Integer; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Image size, placement, etc\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetImageProperties\(Integer, IImageProperties, Boolean, string\)
Sets the image properties of an existing image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetImageProperties(const imageIndex: Integer; imageProperties: <a href="../IImageProperties/index.md">IImageProperties</a>; const usesObjectIndex: Boolean; const objectPath: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image on the sheet array \(1\-based\)|
||**imageProperties**|[IImageProperties](../IImageProperties/index.md)|Image size, placement, etc\.|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\. When you have the object id, you can avoid calling [ObjectIndexToImageIndex](ObjectIndexToImageIndex.md) which is a slow method, by setting this parameter to true\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)


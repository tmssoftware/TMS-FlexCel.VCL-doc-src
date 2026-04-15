---
uid: TXlsBaseChart.GetImageProperties
description: TXlsBaseChart.GetImageProperties
---

# TXlsBaseChart\.GetImageProperties Method

## Overloads

* [TXlsBaseChart\.GetImageProperties\(Integer\)](#txlsbasechartgetimagepropertiesinteger)
* [TXlsBaseChart\.GetImageProperties\(Integer, Boolean, string\)](#txlsbasechartgetimagepropertiesinteger-boolean-string)

# TXlsBaseChart\.GetImageProperties\(Integer\)
Returns image position and size\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.GetImageProperties(const imageIndex: Integer): <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|


## Returns

Image position and size\.

## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.GetImageProperties\(Integer, Boolean, string\)
Returns image position and size\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.GetImageProperties(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string): <a href="../../FlexCel.Core/IImageProperties/index.md">IImageProperties</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|


## Returns

Image position and size\.

## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


---
uid: TXlsBaseChart.ClearImage
description: TXlsBaseChart.ClearImage
---

# TXlsBaseChart\.ClearImage Method

## Overloads

* [TXlsBaseChart\.ClearImage\(Integer\)](#txlsbasechartclearimageinteger)
* [TXlsBaseChart\.ClearImage\(Integer, Boolean, string\)](#txlsbasechartclearimageinteger-boolean-string)

# TXlsBaseChart\.ClearImage\(Integer\)
Clears the image at position imageIndex, leaving an empty white box\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.ClearImage(const imageIndex: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image to clear\. \(1 based\)|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.ClearImage\(Integer, Boolean, string\)
Clears the image at position imageIndex, leaving an empty white box\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.ClearImage(const imageIndex: Integer; const usesObjectIndex: Boolean; const objectPath: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Index of the image to clear\. \(1 based\)|
|const|**usesObjectIndex**|Boolean|If false \(the default\) then imageIndex is an index to the list of images\.<br />When true imageIndex is an index to the list of all objects in the sheet\.|
|const|**objectPath**|string|Path to the object, when the object is grouped with others\. This parameter only has meaning if usesObjectIndex is true\.<br /><br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


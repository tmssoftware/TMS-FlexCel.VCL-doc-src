---
uid: TExcelFile.ObjectPathToImageIndex
description: TExcelFile.ObjectPathToImageIndex
---

# TExcelFile\.ObjectPathToImageIndex Method

Returns the index on the image collection of an object\. **Note that this method is slow** when there are many images, so use it sparingly\.
Whenever possible, prefer the methods that take directly an objectPath instead of converting the objectPath to an imageIndex\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.ObjectPathToImageIndex(const objectIndex: Integer; const objectPath: string): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object\.|
|const|**objectPath**|string|Index to the child object you want find\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"\.<br />You might also use the name of the object as objectpath, like ObjectPathToImageIndex\(\-1, "@myobjectname"\);|


## Returns

\-1 if the object is not an image, else the index on the image collection\.

## See also

* [TExcelFile](../TExcelFile/index.md)


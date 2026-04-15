---
uid: TXlsFile.ObjectPathToImageIndex
description: TXlsFile.ObjectPathToImageIndex
---

# TXlsFile\.ObjectPathToImageIndex Method

Returns the index on the image collection of an object\. **Note that this method is slow** when there are many images, so use it sparingly\.
Whenever possible, prefer the methods that take directly an objectPath instead of converting the objectPath to an imageIndex\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ObjectPathToImageIndex(const objectIndex: Integer; const objectPath: string): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object\.|
|const|**objectPath**|string|Index to the child object you want find\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"\.<br />You might also use the name of the object as objectpath, like ObjectPathToImageIndex\(\-1, "@myobjectname"\);|


## Returns

\-1 if the object is not an image, else the index on the image collection\.

## See also

* [TXlsFile](../TXlsFile/index.md)


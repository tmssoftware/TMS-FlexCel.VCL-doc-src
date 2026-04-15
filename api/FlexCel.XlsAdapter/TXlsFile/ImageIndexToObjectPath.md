---
uid: TXlsFile.ImageIndexToObjectPath
description: TXlsFile.ImageIndexToObjectPath
---

# TXlsFile\.ImageIndexToObjectPath Method

Returns the absolute object path for an image, given an image index\. Note that this method can be slow if there are many objects in the file\.
Whenever possible, prefer the methods that take directly an imageIndex instead of converting the imageIndex to an objectPath\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ImageIndexToObjectPath(const imageIndex: Integer): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image index on the image array\.|


## Returns

Image index on the total objects array\.

## See also

* [TXlsFile](../TXlsFile/index.md)


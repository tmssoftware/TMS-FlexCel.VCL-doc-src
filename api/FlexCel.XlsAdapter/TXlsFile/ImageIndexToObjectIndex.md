---
uid: TXlsFile.ImageIndexToObjectIndex
description: TXlsFile.ImageIndexToObjectIndex
---

# TXlsFile\.ImageIndexToObjectIndex Method

Returns the general index on the object list for an image\. You can use then this index on SendToBack, for example\.
Note that if the image is in a group, this method will return the first object index for the group that contains the image\.
If you want to get the object path to the image instead, look at [TExcelFile.ImageIndexToObjectPath](../../FlexCel.Core/TExcelFile/ImageIndexToObjectPath.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ImageIndexToObjectIndex(const imageIndex: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image index on the image array\.|


## Returns

Image index on the total objects array\.

## See also

* [TXlsFile](../TXlsFile/index.md)


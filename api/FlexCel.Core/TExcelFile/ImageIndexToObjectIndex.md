---
uid: TExcelFile.ImageIndexToObjectIndex
description: TExcelFile.ImageIndexToObjectIndex
---

# TExcelFile\.ImageIndexToObjectIndex Method

Returns the general index on the object list for an image\. You can use then this index on SendToBack, for example\.
Note that if the image is in a group, this method will return the first object index for the group that contains the image\.
If you want to get the object path to the image instead, look at [ImageIndexToObjectPath](ImageIndexToObjectPath.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.ImageIndexToObjectIndex(const imageIndex: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image index on the image array\.|


## Returns

Image index on the total objects array\.

## See also

* [TExcelFile](../TExcelFile/index.md)


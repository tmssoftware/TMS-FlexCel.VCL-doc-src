---
uid: IEmbeddedObjects.ImageIndexToObjectPath
description: IEmbeddedObjects.ImageIndexToObjectPath
---

# IEmbeddedObjects\.ImageIndexToObjectPath Method

Returns the absolute object path for an image, given an image index\. Note that this method can be slow if there are many objects in the file\.
Whenever possible, prefer the methods that take directly an imageIndex instead of converting the imageIndex to an objectPath\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>.ImageIndexToObjectPath(const imageIndex: Integer): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**imageIndex**|Integer|Image index on the image array\.|


## Returns

Image index on the total objects array\.

## See also

* [IEmbeddedObjects](../IEmbeddedObjects/index.md)


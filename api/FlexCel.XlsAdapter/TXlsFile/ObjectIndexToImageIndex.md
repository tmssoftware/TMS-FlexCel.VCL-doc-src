---
uid: TXlsFile.ObjectIndexToImageIndex
description: TXlsFile.ObjectIndexToImageIndex
---

# TXlsFile\.ObjectIndexToImageIndex Method

Returns the index on the image collection of an object\. **Note that this method is slow** when there are many images, so use it sparingly\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ObjectIndexToImageIndex(const objectIndex: Integer): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|General index of the image on the Object collection\.|


## Returns

\-1 if the object is not an image, else the index on the image collection\.

## See also

* [TXlsFile](../TXlsFile/index.md)


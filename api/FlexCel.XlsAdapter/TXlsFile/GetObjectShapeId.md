---
uid: TXlsFile.GetObjectShapeId
description: TXlsFile.GetObjectShapeId
---

# TXlsFile\.GetObjectShapeId Method

Returns the shape id of the object at objectIndex position\. Shape Ids are internal identifiers for the shape, that you can use to uniquely identify a shape\.
Note that the shape id can change when you load the file, once it is loaded, it will remain the same for the shape lifetime\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetObjectShapeId(const objectIndex: Integer): Int64; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Object index\. \(1\-based\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


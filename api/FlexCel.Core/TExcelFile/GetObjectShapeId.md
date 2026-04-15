---
uid: TExcelFile.GetObjectShapeId
description: TExcelFile.GetObjectShapeId
---

# TExcelFile\.GetObjectShapeId Method

Returns the shape id of the object at objectIndex position\. Shape Ids are internal identifiers for the shape, that you can use to uniquely identify a shape\.
Note that the shape id can change when you load the file, once it is loaded, it will remain the same for the shape lifetime\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectShapeId(const objectIndex: Integer): Int64; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Object index\. \(1\-based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


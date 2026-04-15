---
uid: TXlsFile.GetObjectsInRange
description: TXlsFile.GetObjectsInRange
---

# TXlsFile\.GetObjectsInRange Method

Returns a list with all the objects that are completely inside a range of cells\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.GetObjectsInRange(const range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const objectsInRange: <a href="../../FlexCel.Core/TExcelObjectList/index.md">TExcelObjectList</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells where we want to find the objects\.|
|const|**objectsInRange**|[TExcelObjectList](../../FlexCel.Core/TExcelObjectList/index.md)|In this list we will add all the objects found\. Note that the objects will be added to the list, so if you want just the objects in this range, make sure you clear the list before calling this method\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


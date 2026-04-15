---
uid: TExcelFile.GetObjectsInRange
description: TExcelFile.GetObjectsInRange
---

# TExcelFile\.GetObjectsInRange Method

Returns a list with all the objects that are completely inside a range of cells\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectsInRange(const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const objectsInRange: <a href="../TExcelObjectList/index.md">TExcelObjectList</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells where we want to find the objects\.|
|const|**objectsInRange**|[TExcelObjectList](../TExcelObjectList/index.md)|In this list we will add all the objects found\. Note that the objects will be added to the list, so if you want just the objects in this range, make sure you clear the list before calling this method\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


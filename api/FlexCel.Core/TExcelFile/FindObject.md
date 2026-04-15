---
uid: TExcelFile.FindObject
description: TExcelFile.FindObject
---

# TExcelFile\.FindObject Method

Returns the object index for an existing name\. Whenever possible you should prefer to use [FindObjectPath](FindObjectPath.md) instead of this method, since it is faster and finds also objects that are not in the root branch\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.FindObject(const objectName: string): Integer;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectName**|string|Object name to search for\. This is case insensitive\.|


## Returns

\-1 if the object is not found, or the object index otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)


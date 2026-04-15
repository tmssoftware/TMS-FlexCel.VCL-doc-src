---
uid: TXlsFile.GetObjectAnchor
description: TXlsFile.GetObjectAnchor
---

# TXlsFile\.GetObjectAnchor Method

Returns the placement of the object\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetObjectAnchor(const objectIndex: Integer; const objectPath: string): <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"\.<br />You might also use the name of the object as objectpath, like GetObjectAnchor\(\-1, "@myobjectname"\);|


## Returns

Coordinates of the object\.

## See also

* [TXlsFile](../TXlsFile/index.md)


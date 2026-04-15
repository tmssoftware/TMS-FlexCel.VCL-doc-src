---
uid: TXlsBaseChart.GetShapeLinkedCell
description: TXlsBaseChart.GetShapeLinkedCell
---

# TXlsBaseChart\.GetShapeLinkedCell Method

Returns the cell that is linked to the shape\. If the object isn't linked, this method will return null\.
Note that when you change the value in the cell linked to this object, the value of the object will change\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.GetShapeLinkedCell(const objectIndex: Integer; const objectPath: string): string;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|


## Returns

The cell address or name which this shape is linked to, or null if it isn't linked\.

## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


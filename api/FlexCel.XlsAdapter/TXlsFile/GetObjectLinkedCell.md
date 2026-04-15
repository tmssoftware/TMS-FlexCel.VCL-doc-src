---
uid: TXlsFile.GetObjectLinkedCell
description: TXlsFile.GetObjectLinkedCell
---

# TXlsFile\.GetObjectLinkedCell Method

Returns the cell that is linked to the object\. If the object isn't an object that can be linked or it isn't linked, this method will return null\.
Note that when you change the value in the cell linked to this object,  the value of the object will change\.

The sheet returned in the TCellAddress might be null, in which case the reference is to a cell in the same sheet, or it might contain another sheet name\.

Also note that this applies to form objects\. To get the link of a shape like a circle or rectangle, use [TExcelFile.GetShapeLinkedCell](../../FlexCel.Core/TExcelFile/GetShapeLinkedCell.md) instead\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetObjectLinkedCell(const objectIndex: Integer; const objectPath: string): <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

The cell address this object is linked to, or null if it isn't linked\.

## See also

* [TXlsFile](../TXlsFile/index.md)


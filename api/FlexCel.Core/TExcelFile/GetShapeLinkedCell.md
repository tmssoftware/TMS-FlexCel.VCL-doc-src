---
uid: TExcelFile.GetShapeLinkedCell
description: TExcelFile.GetShapeLinkedCell
---

# TExcelFile\.GetShapeLinkedCell Method

Returns the cell that is linked to the shape or image\. If the object isn't linked, this method will return null\.
Note that when you change the value in the cell linked to this object,  the value of the object will change\.
Also note that this method applies to shapes like a rectangle or circle, or an image\. To get the link of a forms object like a combobox or a radiobutton use [GetObjectLinkedCell](GetObjectLinkedCell.md) instead\.


## Remarks

Images behave differently from shapes: A linked shape will change its text with the value of the cells\.
A linked image will change its image, to be an screenshot of the selected range\.
Finally, a linked object like a combobox you can get with [GetObjectLinkedCell](GetObjectLinkedCell.md) will modify the selected item depending on the linked cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetShapeLinkedCell(const objectIndex: Integer; const objectPath: string): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

The cell address or name which this shape is linked to, or null if it isn't linked\.

## See also

* [TExcelFile](../TExcelFile/index.md)


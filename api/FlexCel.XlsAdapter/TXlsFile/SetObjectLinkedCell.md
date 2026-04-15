---
uid: TXlsFile.SetObjectLinkedCell
description: TXlsFile.SetObjectLinkedCell
---

# TXlsFile\.SetObjectLinkedCell Method

Links the object to a cell, if the object can be linked\. If the object is a radio button then all the other radio buttons in the group will be linked to the same cell,  so when the cell changes the radio buttons too, and vice\-versa\. To unlink the cell, make linkedCell null\.


## Remarks

Note that when the object is a radio button, this affects all radio buttons in the same group, not just the first\.
Also this method applies only to "objects" from the "Developer" tab like a button or a radio button\. For shapes, see [TExcelFile.SetShapeLinkedCell](../../FlexCel.Core/TExcelFile/SetShapeLinkedCell.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectLinkedCell(const objectIndex: Integer; const objectPath: string; const linkedCell: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**linkedCell**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell that will be linked to the object\. To unlink the object, make this parameter null\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


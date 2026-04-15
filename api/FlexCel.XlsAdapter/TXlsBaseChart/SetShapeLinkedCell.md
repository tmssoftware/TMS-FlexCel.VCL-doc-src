---
uid: TXlsBaseChart.SetShapeLinkedCell
description: TXlsBaseChart.SetShapeLinkedCell
---

# TXlsBaseChart\.SetShapeLinkedCell Method

Links the shape to a cell, if the shape can be linked\. To unlink the cell, make linkedCell null\.
Note that this method applies to shapes like a rectangle or a circle, not to the link of a forms object like a combobox or a radiobutton\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.SetShapeLinkedCell(const objectIndex: Integer; const objectPath: string; const linkedCell: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**linkedCell**|string|Cell that will be linked to the shape\. To unlink the shape, make this parameter null\. Note that this can be a single cell like "A3" or a name like "myName"\. You can't use a complex formula here like "A1&amp;A2"|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


---
uid: TXlsFile.SetObjectProperties
description: TXlsFile.SetObjectProperties
---

# TXlsFile\.SetObjectProperties Method

Sets all the properties of the shape\. This allows for more complete control than [TExcelFile.SetObjectProperty\(Integer, string, TShapeOption, string\)](../../FlexCel.Core/TExcelFile/SetObjectProperty.md#texcelfilesetobjectpropertyinteger-string-tshapeoption-string) beause it can specify for example a xlsx fill using a theme color, instead of simple RGB fills\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperties(const objectIndex: Integer; const objectPath: string; shapeProperties: <a href="../../FlexCel.Core/IShapeProperties/index.md">IShapeProperties</a>; const applyAnchor: Boolean); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
||**shapeProperties**|[IShapeProperties](../../FlexCel.Core/IShapeProperties/index.md)|All the properties of the object\. You will normally get this value from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean) and then replace the values you want\.|
|const|**applyAnchor**|Boolean|If true, the anchor of the shape properties will be copied too\. If false, the anchor won't change\.<br />False can be used when you want to copy the properties from one object to another, but keep the positions\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


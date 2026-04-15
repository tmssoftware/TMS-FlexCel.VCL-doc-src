---
uid: TXlsFile.SetObjectProperty
description: TXlsFile.SetObjectProperty
---

# TXlsFile\.SetObjectProperty Method

## Overloads

* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Int64\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-int64)
* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Double\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-double)
* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Boolean\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-boolean)
* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, string\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-string)
* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, TDrawingHyperlink\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-tdrawinghyperlink)
* [TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Integer, Boolean\)](#txlsfilesetobjectpropertyinteger-string-tshapeoption-integer-boolean)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Int64\)
Sets a LONG property for an autoshape\. Verify the property expects a LONG\.
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const value: Int64); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\.|
|const|**value**|Int64|Value you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Double\)
Sets a DOUBLE \(Encoded as 16\.16\) property for an autoshape\. Verify the property expects a DOUBLE\.
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const value: Double); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\.|
|const|**value**|Double|Value you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Boolean\)
Sets a BOOLEAN property for an autoshape\. Verify the property expects a BOOLEAN\.
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const value: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\.|
|const|**value**|Boolean|Value you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, string\)
Sets a STRING property for an autoshape\. Verify the property expects a STRING\.
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\. \(like SetObjectText\)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const text: string); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\.|
|const|**text**|string|Text you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, TDrawingHyperlink\)
Sets an Hyperlink property for an autoshape\. Verify the property expects a Hyperlink, currently only [TShapeOption.pihlShape](../../FlexCel.Core/TShapeOption.md) expects hyperlinks\.
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const value: <a href="../../FlexCel.Core/TDrawingHyperlink/index.md">TDrawingHyperlink</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\. For hyperlinks it should be [TShapeOption.pihlShape](../../FlexCel.Core/TShapeOption.md)|
|const|**value**|[TDrawingHyperlink](../../FlexCel.Core/TDrawingHyperlink/index.md)|Value you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetObjectProperty\(Integer, string, TShapeOption, Integer, Boolean\)
Sets a BOOLEAN property for an autoshape\. Verify the property expects a BOOLEAN\.

**This is an advanced method, you probably want to use [TExcelFile.SetObjectProperty\(Integer, string, TShapeOption, Boolean\)](../../FlexCel.Core/TExcelFile/SetObjectProperty.md#texcelfilesetobjectpropertyinteger-string-tshapeoption-boolean) instead\.**
This is an advanced method and should be used with care\. For normal use, you should use one of the standard methods\.
Note that boolean properties are all stored in the same byte of the last property in the set\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectProperty(const objectIndex: Integer; const objectPath: string; const shapeProperty: <a href="../../FlexCel.Core/TShapeOption.md">TShapeOption</a>; const positionInSet: Integer; const value: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**shapeProperty**|[TShapeOption](../../FlexCel.Core/TShapeOption.md)|Property you want to change\. MAKE SURE it is the LAST property in the set\.|
|const|**positionInSet**|Integer|Boolean properties are grouped so all properties on one set are in only one value\. So, the last bool property on the set is the first bit, and so on\. ONLY THE LAST PROPERTY ON THE SET IS PRESENT\.|
|const|**value**|Boolean|Value you want to use\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


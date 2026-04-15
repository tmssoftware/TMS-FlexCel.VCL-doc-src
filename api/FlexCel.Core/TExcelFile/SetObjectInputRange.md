---
uid: TExcelFile.SetObjectInputRange
description: TExcelFile.SetObjectInputRange
---

# TExcelFile\.SetObjectInputRange Method

Sets the input range for a ListBox or a ComboBox\. When applied to other objects, this method does nothing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectInputRange(const objectIndex: Integer; const objectPath: string; const inputRange: <a href="../TCellAddressRange/index.md">TCellAddressRange</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**inputRange**|[TCellAddressRange](../TCellAddressRange/index.md)|Input range for the object\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.SetObjectInputRange
description: TXlsFile.SetObjectInputRange
---

# TXlsFile\.SetObjectInputRange Method

Sets the input range for a ListBox or a ComboBox\. When applied to other objects, this method does nothing\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetObjectInputRange(const objectIndex: Integer; const objectPath: string; const inputRange: <a href="../../FlexCel.Core/TCellAddressRange/index.md">TCellAddressRange</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**inputRange**|[TCellAddressRange](../../FlexCel.Core/TCellAddressRange/index.md)|Input range for the object\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


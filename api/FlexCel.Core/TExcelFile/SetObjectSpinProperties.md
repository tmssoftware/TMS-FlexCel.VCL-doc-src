---
uid: TExcelFile.SetObjectSpinProperties
description: TExcelFile.SetObjectSpinProperties
---

# TExcelFile\.SetObjectSpinProperties Method

Sets the spin properties of an object\. You should apply this only to scrollbars and spinners\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectSpinProperties(const objectIndex: Integer; const objectPath: string; const spinProps: <a href="../TSpinProperties/index.md">TSpinProperties</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**spinProps**|[TSpinProperties](../TSpinProperties/index.md)|Properties of the spinner\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


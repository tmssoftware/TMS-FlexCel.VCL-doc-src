---
uid: TExcelFile.SetObjectSpinValue
description: TExcelFile.SetObjectSpinValue
---

# TExcelFile\.SetObjectSpinValue Method

Sets the position in a scrollbar object\. If the object is linked to a cell, the cell will be updated\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectSpinValue(const objectIndex: Integer; const objectPath: string; const value: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**value**|Integer|Position for the scrollbar\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


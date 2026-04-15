---
uid: TExcelFile.GetObjectMacro
description: TExcelFile.GetObjectMacro
---

# TExcelFile\.GetObjectMacro Method

Returns the macro associated with an object, or null if there is no macro associated\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectMacro(const objectIndex: Integer; const objectPath: string): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

The macro associated with the object, or null if there isn't any macro associated\.

## See also

* [TExcelFile](../TExcelFile/index.md)


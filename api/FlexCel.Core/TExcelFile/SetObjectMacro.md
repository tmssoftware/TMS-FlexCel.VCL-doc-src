---
uid: TExcelFile.SetObjectMacro
description: TExcelFile.SetObjectMacro
---

# TExcelFile\.SetObjectMacro Method

Associates an object with a macro\. While this will normally be used in buttons, you can associate macros to almost any object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetObjectMacro(const objectIndex: Integer; const objectPath: string; const macro: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**macro**|string|Macro that will be associated with the object\. Look at ApiMate to know the exact name you have to enter here\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


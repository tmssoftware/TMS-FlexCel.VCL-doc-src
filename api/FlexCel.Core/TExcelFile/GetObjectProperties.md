---
uid: TExcelFile.GetObjectProperties
description: TExcelFile.GetObjectProperties
---

# TExcelFile\.GetObjectProperties Method

## Overloads

* [TExcelFile\.GetObjectProperties\(Integer, Boolean\)](#texcelfilegetobjectpropertiesinteger-boolean)
* [TExcelFile\.GetObjectProperties\(Integer, string, Boolean\)](#texcelfilegetobjectpropertiesinteger-string-boolean)

# TExcelFile\.GetObjectProperties\(Integer, Boolean\)
Returns information on an object and all of its children\. If the shape doesn't exist, this method returns null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectProperties(const objectIndex: Integer; const getShapeOptions: Boolean): <a href="../IShapeProperties/index.md">IShapeProperties</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**getShapeOptions**|Boolean|When true, shape options will be retrieved\. As this can be a slow operation, only specify true when you really need those options\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetObjectProperties\(Integer, string, Boolean\)
Returns information on an object and all of its children\. If the shape doesn't exist, this method returns null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectProperties(const objectIndex: Integer; const objectPath: string; const getShapeOptions: Boolean): <a href="../IShapeProperties/index.md">IShapeProperties</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"\.<br />You might also use the name of the object as objectpath by writing "@" at the start of the name, like in GetObjectProperties\(\-1, "@myobjectname", true\);|
|const|**getShapeOptions**|Boolean|When true, shape options will be retrieved\. As this can be a slow operation, only specify true when you really need those options\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


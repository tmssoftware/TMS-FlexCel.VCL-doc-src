---
uid: TExcelFile.GetObjectAnchor
description: TExcelFile.GetObjectAnchor
---

# TExcelFile\.GetObjectAnchor Method

## Overloads

* [TExcelFile\.GetObjectAnchor\(Integer\)](#texcelfilegetobjectanchorinteger)
* [TExcelFile\.GetObjectAnchor\(Integer, string\)](#texcelfilegetobjectanchorinteger-string)

# TExcelFile\.GetObjectAnchor\(Integer\)
Returns the placement of the object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectAnchor(const objectIndex: Integer): <a href="../TClientAnchor/index.md">TClientAnchor</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|


## Returns

Coordinates of the object\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetObjectAnchor\(Integer, string\)
Returns the placement of the object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetObjectAnchor(const objectIndex: Integer; const objectPath: string): <a href="../TClientAnchor/index.md">TClientAnchor</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"\.<br />You might also use the name of the object as objectpath, like GetObjectAnchor\(\-1, "@myobjectname"\);|


## Returns

Coordinates of the object\.

## See also

* [TExcelFile](../TExcelFile/index.md)


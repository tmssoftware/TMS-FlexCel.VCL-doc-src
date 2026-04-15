---
uid: TExcelFile.DeleteObject
description: TExcelFile.DeleteObject
---

# TExcelFile\.DeleteObject Method

## Overloads

* [TExcelFile\.DeleteObject\(Integer\)](#texcelfiledeleteobjectinteger)
* [TExcelFile\.DeleteObject\(Integer, string\)](#texcelfiledeleteobjectinteger-string)

# TExcelFile\.DeleteObject\(Integer\)
Deletes the graphic object at objectIndex\. Use it with care, there are some graphics objects you **don't** want to remove \(like comment boxes when you don't delete the associated comment\.\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteObject(const objectIndex: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.DeleteObject\(Integer, string\)
Deletes the graphic object at objectIndex\. Use it with care, there are some graphics objects you **don't** want to remove \(like comment boxes when you don't delete the associated comment\.\)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteObject(const objectIndex: Integer; const objectPath: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties\(Integer, Boolean\)](GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## See also

* [TExcelFile](../TExcelFile/index.md)


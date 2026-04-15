---
uid: TXlsBaseChart.DeleteObject
description: TXlsBaseChart.DeleteObject
---

# TXlsBaseChart\.DeleteObject Method

## Overloads

* [TXlsBaseChart\.DeleteObject\(Integer\)](#txlsbasechartdeleteobjectinteger)
* [TXlsBaseChart\.DeleteObject\(Integer, string\)](#txlsbasechartdeleteobjectinteger-string)

# TXlsBaseChart\.DeleteObject\(Integer\)
Deletes the graphic object at objectIndex\. Use it with care, there are some graphics objects you **don't** want to remove \(like comment boxes when you don't delete the associated comment\.\)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.DeleteObject(const objectIndex: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.DeleteObject\(Integer, string\)
Deletes the graphic object at objectIndex\. Use it with care, there are some graphics objects you **don't** want to remove \(like comment boxes when you don't delete the associated comment\.\)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.DeleteObject(const objectIndex: Integer; const objectPath: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)\.|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


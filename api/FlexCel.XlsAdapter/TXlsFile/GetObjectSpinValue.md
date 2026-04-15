---
uid: TXlsFile.GetObjectSpinValue
description: TXlsFile.GetObjectSpinValue
---

# TXlsFile\.GetObjectSpinValue Method

Returns the current selected value of a scrollbar\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetObjectSpinValue(const objectIndex: Integer; const objectPath: string): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1 based\)|
|const|**objectPath**|string|Index to the child object you want to change the property\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TExcelFile.GetObjectProperties\(Integer, Boolean\)](../../FlexCel.Core/TExcelFile/GetObjectProperties.md#texcelfilegetobjectpropertiesinteger-boolean)<br />If it is "absolute"\(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|


## Returns

The spin position\.

## See also

* [TXlsFile](../TXlsFile/index.md)


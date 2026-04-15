---
uid: TExcelFile.GetCustomTableStyle
description: TExcelFile.GetCustomTableStyle
---

# TExcelFile\.GetCustomTableStyle Method

## Overloads

* [TExcelFile\.GetCustomTableStyle\(string\)](#texcelfilegetcustomtablestylestring)
* [TExcelFile\.GetCustomTableStyle\(Integer\)](#texcelfilegetcustomtablestyleinteger)

# TExcelFile\.GetCustomTableStyle\(string\)
Gets the custom table style with a given name\. If the name doesn't exist, this method returns null\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCustomTableStyle(const name: string): <a href="../ICustomTableStyle/index.md">ICustomTableStyle</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the table style we want to retrieve\. Case insensitive: "NAME" is the same as "name"\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetCustomTableStyle\(Integer\)
Gets the custom table style at position index \(1 based\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetCustomTableStyle(const index: Integer): <a href="../ICustomTableStyle/index.md">ICustomTableStyle</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position for the custom style in the style table\. \(1 based\)\. If index is less than 0 or equal or bigger than [CustomTableStyleCount](CustomTableStyleCount.md) then this method will throw an exception\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.GetCustomTableStyle
description: TXlsFile.GetCustomTableStyle
---

# TXlsFile\.GetCustomTableStyle Method

## Overloads

* [TXlsFile\.GetCustomTableStyle\(string\)](#txlsfilegetcustomtablestylestring)
* [TXlsFile\.GetCustomTableStyle\(Integer\)](#txlsfilegetcustomtablestyleinteger)

# TXlsFile\.GetCustomTableStyle\(string\)
Gets the custom table style with a given name\. If the name doesn't exist, this method returns null\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCustomTableStyle(const name: string): <a href="../../FlexCel.Core/ICustomTableStyle/index.md">ICustomTableStyle</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the table style we want to retrieve\. Case insensitive: "NAME" is the same as "name"\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetCustomTableStyle\(Integer\)
Gets the custom table style at position index \(1 based\)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetCustomTableStyle(const index: Integer): <a href="../../FlexCel.Core/ICustomTableStyle/index.md">ICustomTableStyle</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position for the custom style in the style table\. \(1 based\)\. If index is less than 0 or equal or bigger than [TExcelFile.CustomTableStyleCount](../../FlexCel.Core/TExcelFile/CustomTableStyleCount.md) then this method will throw an exception\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


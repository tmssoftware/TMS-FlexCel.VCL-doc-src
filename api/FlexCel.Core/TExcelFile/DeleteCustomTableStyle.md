---
uid: TExcelFile.DeleteCustomTableStyle
description: TExcelFile.DeleteCustomTableStyle
---

# TExcelFile\.DeleteCustomTableStyle Method

## Overloads

* [TExcelFile\.DeleteCustomTableStyle\(Integer\)](#texcelfiledeletecustomtablestyleinteger)
* [TExcelFile\.DeleteCustomTableStyle\(string\)](#texcelfiledeletecustomtablestylestring)

# TExcelFile\.DeleteCustomTableStyle\(Integer\)
Deletes an existing table style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteCustomTableStyle(const index: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position of the table style to delete \(1 based\)\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.DeleteCustomTableStyle\(string\)
Deletes an existing table style given its name\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.DeleteCustomTableStyle(const name: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the table style to delete\. If the name doesn't exist, this method will throw an exception\.<br />Case insensitive: "NAME" is the same as "name"\.<br /><br />You can use [HasCustomTableStyle](HasCustomTableStyle.md) to check if a table style exists before deleting it\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


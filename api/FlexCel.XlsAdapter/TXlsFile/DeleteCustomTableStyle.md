---
uid: TXlsFile.DeleteCustomTableStyle
description: TXlsFile.DeleteCustomTableStyle
---

# TXlsFile\.DeleteCustomTableStyle Method

## Overloads

* [TXlsFile\.DeleteCustomTableStyle\(Integer\)](#txlsfiledeletecustomtablestyleinteger)
* [TXlsFile\.DeleteCustomTableStyle\(string\)](#txlsfiledeletecustomtablestylestring)

# TXlsFile\.DeleteCustomTableStyle\(Integer\)
Deletes an existing table style\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteCustomTableStyle(const index: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position of the table style to delete \(1 based\)\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.DeleteCustomTableStyle\(string\)
Deletes an existing table style given its name\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteCustomTableStyle(const name: string); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the table style to delete\. If the name doesn't exist, this method will throw an exception\.<br />Case insensitive: "NAME" is the same as "name"\.<br /><br />You can use [TExcelFile.HasCustomTableStyle](../../FlexCel.Core/TExcelFile/HasCustomTableStyle.md) to check if a table style exists before deleting it\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.GetStyle
description: TXlsFile.GetStyle
---

# TXlsFile\.GetStyle Method

## Overloads

* [TXlsFile\.GetStyle\(Integer\)](#txlsfilegetstyleinteger)
* [TXlsFile\.GetStyle\(string, Boolean\)](#txlsfilegetstylestring-boolean)

# TXlsFile\.GetStyle\(Integer\)
Returns the named style at position index for the workbook

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetStyle(const index: Integer): <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of styles \(1 based\)\.|


## Returns

The named style definition\.

## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetStyle\(string, Boolean\)
Returns a named style for the workbook\. You can also use this method to check if a style exists or not\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetStyle(const name: string; const convertToCellStyle: Boolean): <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name for the style\. It might be a user defined name, or a built\-in name\. You can get a list of builtin names with [TExcelFile.GetBuiltInStyleName](../../FlexCel.Core/TExcelFile/GetBuiltInStyleName.md)|
|const|**convertToCellStyle**|Boolean|If true, the returned style will have the "IsStyle" property set to false,  so you can apply this TFlxFormat to a cell\. If false IsStyle will be true and you can use the format definition in style definitions\.<br />Setting this parameter to true is exactly the same as setting it to false and setting "IsStyle" property in the result to false, and also setting the parent of the resulting cell format to the cell style\.|


## Returns

The style definition, or null if the style doesn't exists\.

## See also

* [TXlsFile](../TXlsFile/index.md)


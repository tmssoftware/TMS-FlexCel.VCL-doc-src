---
uid: TExcelFile.GetStyle
description: TExcelFile.GetStyle
---

# TExcelFile\.GetStyle Method

## Overloads

* [TExcelFile\.GetStyle\(Integer\)](#texcelfilegetstyleinteger)
* [TExcelFile\.GetStyle\(string\)](#texcelfilegetstylestring)
* [TExcelFile\.GetStyle\(string, Boolean\)](#texcelfilegetstylestring-boolean)

# TExcelFile\.GetStyle\(Integer\)
Returns the named style at position index for the workbook

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStyle(const index: Integer): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Position in the list of styles \(1 based\)\.|


## Returns

The named style definition\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStyle\(string\)
Returns a named style for the workbook\. You can also use this method to check if a style exists or not\.
The returned style will have the "IsStyle" property set to true, so you can't apply it directly to a cell\.
If you want to apply the result of this method to a cell, use [GetStyle\(string, Boolean\)](GetStyle.md#texcelfilegetstylestring-boolean)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStyle(const name: string): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name for the style\. It might be a user defined name, or a built\-in name\. You can get a list of built\-in names with [GetBuiltInStyleName](GetBuiltInStyleName.md)|


## Returns

The style definition, or null if the style doesn't exists\.

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.GetStyle\(string, Boolean\)
Returns a named style for the workbook\. You can also use this method to check if a style exists or not\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetStyle(const name: string; const convertToCellStyle: Boolean): <a href="../TFlxFormat/index.md">TFlxFormat</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name for the style\. It might be a user defined name, or a built\-in name\. You can get a list of builtin names with [GetBuiltInStyleName](GetBuiltInStyleName.md)|
|const|**convertToCellStyle**|Boolean|If true, the returned style will have the "IsStyle" property set to false,  so you can apply this TFlxFormat to a cell\. If false IsStyle will be true and you can use the format definition in style definitions\.<br />Setting this parameter to true is exactly the same as setting it to false and setting "IsStyle" property in the result to false, and also setting the parent of the resulting cell format to the cell style\.|


## Returns

The style definition, or null if the style doesn't exists\.

## See also

* [TExcelFile](../TExcelFile/index.md)


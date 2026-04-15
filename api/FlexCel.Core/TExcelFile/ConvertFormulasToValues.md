---
uid: TExcelFile.ConvertFormulasToValues
description: TExcelFile.ConvertFormulasToValues
---

# TExcelFile\.ConvertFormulasToValues Method

## Overloads

* [TExcelFile\.ConvertFormulasToValues\(Boolean\)](#texcelfileconvertformulastovaluesboolean)
* [TExcelFile\.ConvertFormulasToValues\(Boolean, Boolean\)](#texcelfileconvertformulastovaluesboolean-boolean)

# TExcelFile\.ConvertFormulasToValues\(Boolean\)
Use it to convert formulas to their values\. It can be useful if for example you are copying the sheet to another workbook, and you don't want any references to it\. NOTE: You will probably want to use [ConvertExternalNamesToRefErrors\(Boolean\)](ConvertExternalNamesToRefErrors.md#texcelfileconvertexternalnamestoreferrorsboolean) too, to convert named ranges besides the formulas\.

Also note that if you want to convert a whole file, you need to call ConvertFormulasToValues in every sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ConvertFormulasToValues(const onlyExternal: Boolean); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**onlyExternal**|Boolean|When true, it will only convert the formulas that do not refer to the same sheet\.<br />For example "=A1\+Sheet2\!A1" will be converted, but "=A2\+A3" will not\.<br />|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.ConvertFormulasToValues\(Boolean, Boolean\)
Use it to convert formulas to their values\. It can be useful if for example you are copying the sheet to another workbook, and you don't want any references to it\. NOTE: You will probably want to use [ConvertExternalNamesToRefErrors\(Boolean\)](ConvertExternalNamesToRefErrors.md#texcelfileconvertexternalnamestoreferrorsboolean) too, to convert named ranges besides the formulas\.

Also note that if you want to convert a whole file, you need to call ConvertFormulasToValues in every sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ConvertFormulasToValues(const onlyExternal: Boolean; const recalcBeforeConverting: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**onlyExternal**|Boolean|When true, it will only convert the formulas that do not refer to the same sheet\.<br />For example "=A1\+Sheet2\!A1" will be converted, but "=A2\+A3" will not\.<br />|
|const|**recalcBeforeConverting**|Boolean|If true \(the default\), FlexCel will try to recalculate the file before converting the formulas\.<br />Use false when for any reason FlexCel can't recalculate the values \(for example if you have links to other files that don't exist anymore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


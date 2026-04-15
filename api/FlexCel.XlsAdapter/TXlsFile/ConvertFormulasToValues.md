---
uid: TXlsFile.ConvertFormulasToValues
description: TXlsFile.ConvertFormulasToValues
---

# TXlsFile\.ConvertFormulasToValues Method

Use it to convert formulas to their values\. It can be useful if for example you are copying the sheet to another workbook, and you don't want any references to it\. NOTE: You will probably want to use [TExcelFile.ConvertExternalNamesToRefErrors\(Boolean\)](../../FlexCel.Core/TExcelFile/ConvertExternalNamesToRefErrors.md#texcelfileconvertexternalnamestoreferrorsboolean) too, to convert named ranges besides the formulas\.

Also note that if you want to convert a whole file, you need to call ConvertFormulasToValues in every sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.ConvertFormulasToValues(const onlyExternal: Boolean; const recalcBeforeConverting: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**onlyExternal**|Boolean|When true, it will only convert the formulas that do not refer to the same sheet\.<br />For example "=A1\+Sheet2\!A1" will be converted, but "=A2\+A3" will not\.<br />|
|const|**recalcBeforeConverting**|Boolean|If true \(the default\), FlexCel will try to recalculate the file before converting the formulas\.<br />Use false when for any reason FlexCel can't recalculate the values \(for example if you have links to other files that don't exist anymore\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


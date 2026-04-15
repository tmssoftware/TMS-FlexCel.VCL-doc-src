---
uid: TExcelFile.ConvertExternalNamesToRefErrors
description: TExcelFile.ConvertExternalNamesToRefErrors
---

# TExcelFile\.ConvertExternalNamesToRefErrors Method

## Overloads

* [TExcelFile\.ConvertExternalNamesToRefErrors](#texcelfileconvertexternalnamestoreferrors)
* [TExcelFile\.ConvertExternalNamesToRefErrors\(Boolean\)](#texcelfileconvertexternalnamestoreferrorsboolean)

# TExcelFile\.ConvertExternalNamesToRefErrors
Use it to convert the external names in a sheet to \#REF\! \. It can be useful when you need to remove all external links in a file\.
NOTE: You will probably want to use [ConvertFormulasToValues\(Boolean\)](ConvertFormulasToValues.md#texcelfileconvertformulastovaluesboolean) too\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ConvertExternalNamesToRefErrors; overload;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.ConvertExternalNamesToRefErrors\(Boolean\)
Use it to convert the external names in a sheet to \#REF\! \. It can be useful when you need to remove all external links in a file\.
NOTE: You will probably want to use [ConvertFormulasToValues\(Boolean\)](ConvertFormulasToValues.md#texcelfileconvertformulastovaluesboolean) too\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.ConvertExternalNamesToRefErrors(const recalcBeforeConverting: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**recalcBeforeConverting**|Boolean|If true \(the default\), FlexCel will try to recalculate the file before converting the formulas\.<br />Use false when for any reason FlexCel can't recalculate the values \(for example if you have links to other files that don't exist anymore\)|


## See also

* [TExcelFile](../TExcelFile/index.md)


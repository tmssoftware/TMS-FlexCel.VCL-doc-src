---
uid: TXlsFile.ConvertExternalNamesToRefErrors
description: TXlsFile.ConvertExternalNamesToRefErrors
---

# TXlsFile\.ConvertExternalNamesToRefErrors Method

Use it to convert the external names in a sheet to \#REF\! \. It can be useful when you need to remove all external links in a file\.
NOTE: You will probably want to use [TExcelFile.ConvertFormulasToValues\(Boolean\)](../../FlexCel.Core/TExcelFile/ConvertFormulasToValues.md#texcelfileconvertformulastovaluesboolean) too\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.ConvertExternalNamesToRefErrors(const recalcBeforeConverting: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**recalcBeforeConverting**|Boolean|If true \(the default\), FlexCel will try to recalculate the file before converting the formulas\.<br />Use false when for any reason FlexCel can't recalculate the values \(for example if you have links to other files that don't exist anymore\)|


## See also

* [TXlsFile](../TXlsFile/index.md)


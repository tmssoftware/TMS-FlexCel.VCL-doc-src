---
uid: TXlsFile.OptionsForceUseCheckCompatibility
description: TXlsFile.OptionsForceUseCheckCompatibility
---

# TXlsFile.OptionsForceUseCheckCompatibility Property

When the option [TExcelFile.OptionsCheckCompatibility](../../FlexCel.Core/TExcelFile/OptionsCheckCompatibility.md) is true, Excel will refuse to austosave the file\.
To avoid a confusing situation where Excel refuses to autosave the file and shows a vague warning about an "older file format", [TExcelFile.OptionsCheckCompatibility](../../FlexCel.Core/TExcelFile/OptionsCheckCompatibility.md) is ignored by FlexCel\.



In order to force FlexCel to save [TExcelFile.OptionsCheckCompatibility](../../FlexCel.Core/TExcelFile/OptionsCheckCompatibility.md) to the file \(thus disabling the "Autosave" function\) you need to set this property to true besides [TExcelFile.OptionsCheckCompatibility](../../FlexCel.Core/TExcelFile/OptionsCheckCompatibility.md)\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.OptionsForceUseCheckCompatibility: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


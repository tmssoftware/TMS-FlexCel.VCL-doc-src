---
uid: TExcelFile.OptionsForceUseCheckCompatibility
description: TExcelFile.OptionsForceUseCheckCompatibility
---

# TExcelFile.OptionsForceUseCheckCompatibility Property

When the option [OptionsCheckCompatibility](OptionsCheckCompatibility.md) is true, Excel will refuse to austosave the file\.
To avoid a confusing situation where Excel refuses to autosave the file and shows a vague warning about an "older file format", [OptionsCheckCompatibility](OptionsCheckCompatibility.md) is ignored by FlexCel\.



In order to force FlexCel to save [OptionsCheckCompatibility](OptionsCheckCompatibility.md) to the file \(thus disabling the "Autosave" function\) you need to set this property to true besides [OptionsCheckCompatibility](OptionsCheckCompatibility.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.OptionsForceUseCheckCompatibility: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.OptionsCheckCompatibility
description: TXlsFile.OptionsCheckCompatibility
---

# TXlsFile.OptionsCheckCompatibility Property

Whether the "Check for compatibility" dialog will pop up when saving as xls in Excel 2007 or newer\.
This option only applies to Excel 2007 or newer\.

**Important:** When this option is true, Excel will refuse to enable "Autosave" and upload the files to OneDrive \(Autosave is the first option in the title bar in Excel 2019\)\. If true, you will get a message:

"How do I turn on Autosave?
Before Autosave can save your file, you need to fix the following:
This file was created in an older file format\. Please select File > Save As to update the file format\."

So in order to avoid accidentally setting this option true and preventing the Autosave function, **FlexCel will ignore this setting in xlsx files unless you also set [TExcelFile.OptionsForceUseCheckCompatibility](../../FlexCel.Core/TExcelFile/OptionsForceUseCheckCompatibility.md) to true**

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.OptionsCheckCompatibility: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


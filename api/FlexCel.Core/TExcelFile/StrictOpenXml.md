---
uid: TExcelFile.StrictOpenXml
description: TExcelFile.StrictOpenXml
---

# TExcelFile.StrictOpenXml Property

Read this file to know if the xlsx file loaded by FlexCel is a normal xlsx file or a "Strict Open XML file"\.
Set this property  to make FlexCel save as strict or normal open xlsx file\.

This property has no effect in xls files, only in xlsx\. If you are not sure about what a strict open xml file is, just keep this property false and FlexCel will output normal xlsx files\.

**IMPORTANT:**FlexCel works by preserving a lot of stuff it doesn't know about, and that stuff might be valid in normal files and invalid in strict files or vice\-versa\. So if you open an strict file and save it as normal, or open a normal file and save it as strict, it might happen that FlexCel preserves some records or namespaces that are not allowed in the new format\. Given this, you shouldn't use this property to change the type of existing files, except for simple files or files that you created yourself with [NewFile](NewFile.md)\.
You should normally read strict files and save them as strict, or read normal files and save them as normal\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.StrictOpenXml: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


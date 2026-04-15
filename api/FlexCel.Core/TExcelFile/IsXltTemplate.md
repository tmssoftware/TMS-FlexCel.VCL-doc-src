---
uid: TExcelFile.IsXltTemplate
description: TExcelFile.IsXltTemplate
---

# TExcelFile.IsXltTemplate Property

Determines if the file is a template \(xlt format instead of xls, xltx instead of xlsx, or xltm instead of xlsm\)\. Both file formats are nearly identical, but there is an extra record needed so the file is a proper xlt template\. Note that when saving to a file, FlexCel can detect if this is a template from the  extension, and so if you save to \*\.xlt, \*\.xltx or \*\.xltm the file will be saved as template, even if this property is false\.
When saving to a stream, you need to set this property correctly because FlexCel can't guess it from the filename\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.IsXltTemplate: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.GetDefaultFormatNormalStyle
description: TExcelFile.GetDefaultFormatNormalStyle
---

# TExcelFile.GetDefaultFormatNormalStyle Property

Returns Excel standard format for the normal style\. "Normal" style applies to the headers "A", "B" \.\.\. at the top of the columns and "1", "2"\.\.\. at the left of the rows\. This method is the same as calling  *xls\.GetStyle\(xls\.GetBuiltInStyleName\(TBuiltInStyle\.Normal, 0\)\)* You normally will want to use [GetDefaultFormat](GetDefaultFormat.md) instead of this method\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.GetDefaultFormatNormalStyle: <a href="../TFlxFormat/index.md">TFlxFormat</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


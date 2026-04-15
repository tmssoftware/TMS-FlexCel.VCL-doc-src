---
uid: TExcelFile.DefaultRowHidden
description: TExcelFile.DefaultRowHidden
---

# TExcelFile.DefaultRowHidden Property

When this property is true, rows with no data are hidden by default\.
Note that this property only affects the visibility of empty rows\. If for example row 6 is empty and you have this property true, then row 6 will be hidden\. But if you write any value in a cell in row 6, then the row won't be empty anymore, and it won't be hidden anymore either\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.DefaultRowHidden: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


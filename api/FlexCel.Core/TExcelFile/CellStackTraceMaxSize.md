---
uid: TExcelFile.CellStackTraceMaxSize
description: TExcelFile.CellStackTraceMaxSize
---

# TExcelFile.CellStackTraceMaxSize Property

Defines what is the maximum number of entries returned in the stack trace when calling [RecalcAndVerify](RecalcAndVerify.md)\.
In order to keep the stack trace not too big this number is limited, but if you need a bigger stack trace to see the full loop of cells you can increase this number\. Note that if you want to calculate linked files, you need to set the property [TWorkspace.CellStackTraceMaxSize](../TWorkspace/CellStackTraceMaxSize.md) instead and it will affect all workbooks\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.CellStackTraceMaxSize: Integer</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


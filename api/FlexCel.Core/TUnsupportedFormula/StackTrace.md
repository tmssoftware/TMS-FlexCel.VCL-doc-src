---
uid: TUnsupportedFormula.StackTrace
description: TUnsupportedFormula.StackTrace
---

# TUnsupportedFormula.StackTrace Property

This property only has a value is the error is [TUnsupportedFormulaErrorType.CircularReference](../TUnsupportedFormulaErrorType.md)\. It contains a list of all the cells that lead to this cell having to recalculate itself\. Note that this stack is limited to the last [TExcelFile.CellStackTraceMaxSize](../TExcelFile/CellStackTraceMaxSize.md) elements to avoid consuming too much memory\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TUnsupportedFormula/index.md">TUnsupportedFormula</a>.StackTrace: TArray&lt;<a href="../TCellAddressWithFileName/index.md">TCellAddressWithFileName</a>&gt;</code></pre>

## See also

* [TUnsupportedFormula](../TUnsupportedFormula/index.md)


---
uid: TExcelFile.AllowEnteringUnknownFunctionsAndNames
description: TExcelFile.AllowEnteringUnknownFunctionsAndNames
---

# TExcelFile.AllowEnteringUnknownFunctionsAndNames Property

Whenever you try to use an unknown function in a formula, like "=MYFUNCTION\(\)", FlexCel will raise an Exception\. Same happens with unknown names\.
This is normally the expected behavior, so you don't enter a misspelled name by mistake, and you can add used defined function to FlexCel so it understands it\.


But in some cases, you might want to allow any function to be entered, no matter if is known or not: Excel behaves this way\.
For those cases, set this property to true\. The unknown functions will return \#NAME? as formula result\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.AllowEnteringUnknownFunctionsAndNames: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


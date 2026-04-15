---
uid: TDataValidationInfo.ExplicitList
description: TDataValidationInfo.ExplicitList
---

# TDataValidationInfo.ExplicitList Property

If true, [FirstFormula](FirstFormula.md) contains a list of values\.
In this case, Formula1 **must** be a formula of the type: ="string", where string is a list of values separated by Character\(0\)\.
For example, in C\# Formula1 could be: *="Apples\\0Lemmons\\0Melons*   In Delphi\.NET, Formula1 could be: *'="Apples' \+ \#0 \+ 'Lemmons' \+ \#0 \+ 'Melons'*

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDataValidationInfo/index.md">TDataValidationInfo</a>.ExplicitList: Boolean</code></pre>

## See also

* [TDataValidationInfo](../TDataValidationInfo/index.md)


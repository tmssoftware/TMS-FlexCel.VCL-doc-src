---
uid: IConditionalCellIsRule.Formula2
description: IConditionalCellIsRule.Formula2
---

# IConditionalCellIsRule.Formula2 Property

The second formula to be evaluated\. Note that this formula is only used if the condition needs more than one parameter \(for example when condition is "Between"\)\.
If using a condition with only one parameter, you can leave this formula to null\.

Note that with **relative** references, we always consider "A1" to be the cell where the format is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IConditionalCellIsRule/index.md">IConditionalCellIsRule</a>.Formula2: string</code></pre>

## See also

* [IConditionalCellIsRule](../IConditionalCellIsRule/index.md)


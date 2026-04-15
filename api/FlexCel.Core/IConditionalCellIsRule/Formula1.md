---
uid: IConditionalCellIsRule.Formula1
description: IConditionalCellIsRule.Formula1
---

# IConditionalCellIsRule.Formula1 Property

The first formula to be evaluated\. When the condition needs only one parameter \(for example when condition is "Equal"\) this is the only formula that is used\.

Note that with **relative** references, we always consider "A1" to be the cell where the format is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IConditionalCellIsRule/index.md">IConditionalCellIsRule</a>.Formula1: string</code></pre>

## See also

* [IConditionalCellIsRule](../IConditionalCellIsRule/index.md)


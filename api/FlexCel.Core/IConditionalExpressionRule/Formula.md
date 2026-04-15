---
uid: IConditionalExpressionRule.Formula
description: IConditionalExpressionRule.Formula
---

# IConditionalExpressionRule.Formula Property

The formula to be evaluated\. The conditional format will be applied when it evaluates to true\.

Note that with **relative** references, we always consider "A1" to be the cell where the format is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


In Icon sets, Data bars and Color Scales, the formula specifies if the conditional format is applied or not\.
This is not an option in the Excel UI, but you can specify it in the file and Excel will obey it\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IConditionalExpressionRule/index.md">IConditionalExpressionRule</a>.Formula: string</code></pre>

## See also

* [IConditionalExpressionRule](../IConditionalExpressionRule/index.md)


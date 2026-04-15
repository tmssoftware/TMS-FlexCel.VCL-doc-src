---
uid: IConditionalExpressionRule
description: IConditionalExpressionRule
---

# IConditionalExpressionRule Interface

A conditional format rule specified by a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IConditionalExpressionRule = interface(<a href="../IConditionalFormatStandardDefRule/index.md">IConditionalFormatStandardDefRule</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Formula](Formula.md)|The formula to be evaluated\. The conditional format will be applied when it evaluates to true\.<br /><br />Note that with **relative** references, we always consider "A1" to be the cell where the format is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br /><br /><br />In Icon sets, Data bars and Color Scales, the formula specifies if the conditional format is applied or not\.<br />This is not an option in the Excel UI, but you can specify it in the file and Excel will obey it\.<br /><br />|



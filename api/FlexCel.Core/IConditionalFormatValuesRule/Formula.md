---
uid: IConditionalFormatValuesRule.Formula
description: IConditionalFormatValuesRule.Formula
---

# IConditionalFormatValuesRule.Formula Property

The formula to be evaluated\. The conditional format will be displayed when it evaluates to true or a non zero value\.
If the formula equals to 0 or false, the conditional format won't be shown\. Note that from Excel you can't set a formula, it will always be empty for databars, iconsets or colorscales\. But if you set a formula in the xlsx file, it will be  used by Excel and preserved when saved, even if Excel won't display it\.

Note that with **relative** references, we always consider "A1" to be the cell where the format is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../IConditionalFormatValuesRule/index.md">IConditionalFormatValuesRule</a>.Formula: string</code></pre>

## See also

* [IConditionalFormatValuesRule](../IConditionalFormatValuesRule/index.md)


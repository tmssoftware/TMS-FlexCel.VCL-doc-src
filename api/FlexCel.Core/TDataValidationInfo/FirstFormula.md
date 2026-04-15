---
uid: TDataValidationInfo.FirstFormula
description: TDataValidationInfo.FirstFormula
---

# TDataValidationInfo.FirstFormula Property

Formula for the first condition of the data validation\. The text of the formula is limited to 255 characters\.
If [ExplicitList](ExplicitList.md) is true, this formula can contain a list of values\.

Note that with **relative** references, we always consider "A1" to be the cell where the data validation is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


## Remarks

If this formula refers to a cell range, you can get the cell range by calling [TExcelFile.RecalcRange](../TExcelFile/RecalcRange.md)\.

To get the text for a particular cell, use [TExcelFile.OffsetRelativeFormula](../TExcelFile/OffsetRelativeFormula.md)\.

To get the result of evaluating the formula, use [TExcelFile.RecalcRelativeFormula](../TExcelFile/RecalcRelativeFormula.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDataValidationInfo/index.md">TDataValidationInfo</a>.FirstFormula: string</code></pre>

## See also

* [TDataValidationInfo](../TDataValidationInfo/index.md)


---
uid: TXlsNamedRange.RangeFormula
description: TXlsNamedRange.RangeFormula
---

# TXlsNamedRange.RangeFormula Field

This is a formula defining the range\. It can be used to define complex ranges\.
For example you can use "=Sheet1\!$A:$B,Sheet1\!$1:$2"\.
When this parameter is set, SheetIndex, Left, Top, Right and Bottom properties have no meaning\.

Note that with **relative** references, we always consider "A1" to be the cell where the name is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.
For example "=A1048575" will evaluate to B7 when evaluated in B8\.


## Remarks

In latest FlexCel versions, you \*can\* use ranges like "A:B" instead \(A1:B65536\)\. Using "A:B" form is preferred, since it will work also in Excel 2007\.



If this formula refers to a cell range, you can get the cell range by calling [TExcelFile.RecalcRange](../TExcelFile/RecalcRange.md)\.

To get the text for a particular cell, use [TExcelFile.OffsetRelativeFormula](../TExcelFile/OffsetRelativeFormula.md)\.

To get the result of evaluating the formula, use [TExcelFile.RecalcRelativeFormula](../TExcelFile/RecalcRelativeFormula.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs"><a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.RangeFormula: string;</code></pre>

## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)


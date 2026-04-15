---
uid: TUdfEventArgs
description: TUdfEventArgs
---

# TUdfEventArgs Class

Encapsulates the parameters to send to a user Defined Function for evaluation\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUdfEventArgs = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[Xls](Xls.md)|ExcelFile that has the formula being evaluated\. You might change its ActiveSheet property inside this method and there is no need to restore it back\.<br />|
|[Sheet](Sheet.md)|Index of the sheet where the formula is located\. This value only has meaning when evaluating formulas in cells\. \(Not when for example evaluating formulas inside named ranges\)|
|[Row](Row.md)|Row index where the formula is located\. This value only has meaning when evaluating formulas in cells\. \(Not when for example evaluating formulas inside named ranges\)|
|[Col](Col.md)|Column index where the formula is located\. This value only has meaning when evaluating formulas in cells\. \(Not when for example evaluating formulas inside named ranges\)|



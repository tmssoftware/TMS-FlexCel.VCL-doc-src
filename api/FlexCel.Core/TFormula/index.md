---
uid: TFormula
description: TFormula
---

# TFormula Record

An Excel formula\. Use this class to pass a formula to an Excel sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFormula = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Span](Span.md)|For multicell formulas \(like an array formula entered over more than one cell\) this property says how many rows and columns the formula uses\. Normal formulas will span one single cell|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tformulacreate)<br />  [Create\(string\)](Create.md#tformulacreatestring)<br />  [Create\(string, TSingleFormulaValue\)](Create.md#tformulacreatestring-tsingleformulavalue)<br />  [Create\(string, TSingleFormulaValue, TFormulaSpan\)](Create.md#tformulacreatestring-tsingleformulavalue-tformulaspan)<br />|
|[Null](Null.md)|Creates an undefined Excel formula|
|[ToString](ToString.md)|Returns the formula result as a string\.|
|[Equals](Equals.md)|Returns true if obj is equal to this instance\.<br />|
|[GetHashCode](GetHashCode.md)|Hashcode of the formula\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Text](Text.md)|The formula text, as it is written on Excel\. It must begin with "=" or "\{" for array formulas\.<br />|
|[FormulaResult](FormulaResult.md)|The formula result\.<br />|



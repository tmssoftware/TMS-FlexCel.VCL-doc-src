---
uid: TFormulaSpan
description: TFormulaSpan
---

# TFormulaSpan Record

This structure is used in formulas that span more than one cell, like some array formulas, or "what\-if" table formulas\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFormulaSpan = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tformulaspancreate)<br />  [Create\(Integer, Integer, Boolean\)](Create.md#tformulaspancreateinteger-integer-boolean)<br />|
|[Equals](Equals.md)|Returns true of the 2 FormulaSpans are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[RowSpan](RowSpan.md)|How many rows the formula will use\.<br />|
|[ColSpan](ColSpan.md)|How many columns the formula will use\.<br />|
|[IsTopLeft](IsTopLeft.md)|Indicates if this is the first formula of the array\. Only the formula that is at the top left cell of the group will be used when setting a formula\. Other formulas will be ignored, so you can copy  formulas in a loop from one place to the other without worring if the cell is at the top left or not\.<br />|
|[IsOneCell](IsOneCell.md)|Returns true if this formula spans over a single cell\. \(the most usual case\)|



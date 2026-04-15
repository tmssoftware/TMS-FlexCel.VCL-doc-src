---
uid: TSpinProperties
description: TSpinProperties
---

# TSpinProperties Record

Spin properties of a scrollbar, spinner, listbox or combobox\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TSpinProperties = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Min](Min.md)|Minimum value for the spinner/scrollbar\.<br />|
|[Max](Max.md)|Maximum value for the spinner/scrollbar\.<br />|
|[Incr](Incr.md)|How much the scrollbar moves when you press the up or down arrow\. You will probably want to keep this at 1\.<br />|
|[Page](Page.md)|How much the scrollbar moves when you press pgup/down\.<br />|
|[Dx](Dx.md)|Width of the scrollbar\. It should normally be 16\.<br />|
|[IsHorizontal](IsHorizontal.md)|If used in a scrollbar, this property defines if the scrollbar is horizontal or vertical\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tspinpropertiescreate)<br />  [Create\(Integer, Integer, Integer, Integer\)](Create.md#tspinpropertiescreateinteger-integer-integer-integer)<br />  [Create\(Integer, Integer, Integer, Integer, Integer\)](Create.md#tspinpropertiescreateinteger-integer-integer-integer-integer)<br />  [Create\(Integer, Integer, Integer, Integer, Integer, Boolean\)](Create.md#tspinpropertiescreateinteger-integer-integer-integer-integer-boolean)<br />|
|[Equals](Equals.md)|Returns true if both objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|Hashcode for the object\.<br />|
|[Clone](Clone.md)|Creates a copy of the data\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|



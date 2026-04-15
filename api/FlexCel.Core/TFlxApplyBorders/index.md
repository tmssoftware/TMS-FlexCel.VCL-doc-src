---
uid: TFlxApplyBorders
description: TFlxApplyBorders
---

# TFlxApplyBorders Record

Border style for a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxApplyBorders = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Left](Left.md)|Left border\.<br />|
|[Right](Right.md)|Right border\.<br />|
|[Top](Top.md)|Top border\.<br />|
|[Bottom](Bottom.md)|Bottom border\.<br />|
|[Diagonal](Diagonal.md)|Diagonal border\.<br />|
|[DiagonalStyle](DiagonalStyle.md)|When defined, there will be one or two diagonal lines across the cell\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflxapplyborderscreate)<br />  [Create\(Boolean\)](Create.md#tflxapplyborderscreateboolean)<br />|
|[SetAllMembers](SetAllMembers.md)|Sets all members to true or false|
|[Apply](Apply.md)|This method will modify existingFormat with the properties from newFormat that are specified on this class|
|[Clone](Clone.md)|Returns a deep copy of the border\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hash code of the object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[IsEmpty](IsEmpty.md)|Returns true if the format does not apply any setting\.<br />|



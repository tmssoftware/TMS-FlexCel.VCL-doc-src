---
uid: TXls3DRange
description: TXls3DRange
---

# TXls3DRange Record

A 3d Excel range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXls3DRange = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[HasValue](HasValue.md)|False if the record doesn't have a defined value\. When this field is false, the values of the other fields don't matter\.<br />|
|[FileName](FileName.md)|Filename if the range is in a different file\.<br />|
|[Top](Top.md)|Top of the range\.<br />|
|[Left](Left.md)|Left of the range\.<br />|
|[Bottom](Bottom.md)|Bottom of the range\.<br />|
|[Right](Right.md)|Right of the range\.<br />|
|[Sheet2](Sheet2.md)|Second sheet of the range\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#txls3drangecreate)<br />  [Create\(TCoreExcelFile, string\)](Create.md#txls3drangecreatetcoreexcelfile-string)<br />  [Create\(Integer, Integer, Integer, Integer, Integer, Integer\)](Create.md#txls3drangecreateinteger-integer-integer-integer-integer-integer)<br />  [Create\(string, Integer, Integer, Integer, Integer, Integer, Integer\)](Create.md#txls3drangecreatestring-integer-integer-integer-integer-integer-integer)<br />|
|[SetRange3DRef](SetRange3DRef.md)|Sets the value of the 3d range based on the string that defines the range in A1 notation\.<br />|
|[TrySetRange3DRef](TrySetRange3DRef.md)|Tries to set the value of the 3d range based on the string that defines the range in A1 notation\. If the name can't be set, no data is modified and this method returns false\.<br />|
|[Null](Null.md)|Creates a null range\.<br />|
|[Equals](Equals.md)|Returns true if both objects are equal\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\. This is the inverse of [HasValue](HasValue.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[IsOneCell](IsOneCell.md)|Returns true if the range has only one cell\.<br />|



---
uid: TLookupFieldDefinition
description: TLookupFieldDefinition
---

# TLookupFieldDefinition Record

Encapsulates the data for a lookup tag in a report\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TLookupFieldDefinition = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new lookupfield definition\. Fields will be copied\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hash code of this object\.<br />|
|[Equals](Equals.md)|Returns true if both structs are the same\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[KeyFields](KeyFields.md)|The key fields in the lookup\.<br />|
|[ResultField](ResultField.md)|The result field for the lookup\.<br />|
|[OriginalKeyFields&#8203;Definition](OriginalKeyFieldsDefinition.md)|The key fields definition as it is written in the lookup tag\. You will normally not need this data\.<br />|



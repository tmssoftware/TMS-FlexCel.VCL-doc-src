---
uid: TMasterDetailLink
description: TMasterDetailLink
---

# TMasterDetailLink Record

A parent table and a parent field used on a master\-detail relationship\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TMasterDetailLink = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of TMasterDetailLink with the given values\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ParentDataSource](ParentDataSource.md)|A table that is acting as a master on a master detail relationship\.<br />|
|[ParentField](ParentField.md)|Column index of the key that acts as primary key on the relationship\.<br />|
|[ChildFieldName](ChildFieldName.md)|Column name on the detail dataset that is related with [ParentField](ParentField.md)|



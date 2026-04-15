---
uid: TDataConnectionTable
description: TDataConnectionTable
---

# TDataConnectionTable Class

Specifies the HTML table to import\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionTable = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[TableName](TableName.md)|This element is used to specify an HTML table to import by name\. If the tables are not named, they shall be specified with the [TableIndex](TableIndex.md) property instead\. If neither this property or [TableIndex](TableIndex.md) are given, the table is considered missing\.<br />|
|[TableIndex](TableIndex.md)|Index of the HTML table that is going to be imported\. this is used if no [TableName](TableName.md) is specified\.<br />\. If neither this property or [TableName](TableName.md) are given, the table is considered missing\.<br />|



---
uid: TXmlMapSchema
description: TXmlMapSchema
---

# TXmlMapSchema Class

Stores the schemas for a particular XML map object\. There can be multiple Schema elements in a workbook, one for each XML map\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXmlMapSchema = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same values\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Id](Id.md)|Identifies the schema collection used to define a particular XML map object\.<br />|
|[SchemaRef](SchemaRef.md)|The schemaRef attribute is used in the specific case where the schema definition happens to include another schema file that contributes to the same namespace\.The value of this attribute is the relative path to a "root" schema file on disk which in turn references the other schema files contributing type definitions to the same namespace\.<br />|
|[Namespace](Namespace.md)|Namespace used by the schema\.<br />|
|[Language](Language.md)|Specifies the media type of the schema language\.<br />|
|[Xml](Xml.md)|Actual XML defining the schema\.<br />|



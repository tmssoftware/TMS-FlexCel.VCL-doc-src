---
uid: TDataConnectionTextField
description: TDataConnectionTextField
---

# TDataConnectionTextField Class

This element specifies field settings for text import\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionTextField = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Position](Position.md)|The character position the field starts at for fixed\-length fields\. The index is 0\-based\. Subsequent textField elements or carriage returns in the text stream serve to denote endpoints for text fields\.<br />|
|[FieldType](FieldType.md)|Specifies the field Type\. When text is imported into cells in the worksheet, the data in the cells are converted to the field type defined here\.<br />Types can be specified by the user, or determined algorithmically via heuristics\.<br />|



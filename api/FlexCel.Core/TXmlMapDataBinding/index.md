---
uid: TXmlMapDataBinding
description: TXmlMapDataBinding
---

# TXmlMapDataBinding Class

Specifies how the XML binding works\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXmlMapDataBinding = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Assign](Assign.md)|Copies an existing databinding into this object, clearing any existing data\.<br />|
|[Equals](Equals.md)|Returns true if both databindings are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataBindingName](DataBindingName.md)|Specifies the name for the binding\. Must be unique\.<br />|
|[FileBinding](FileBinding.md)|If true the binding must be recovered from a file and the path to the file is in the connection element\.<br />|
|[ConnectionID](ConnectionID.md)|Connection id for an external connection\. Must exist if [FileBinding](FileBinding.md) is true\.<br />|
|[FileBindingName](FileBindingName.md)|Name of the file binding\. Must be unique\.<br />|
|[DataBindingLoadMode](DataBindingLoadMode.md)|Loading mode for this databinding\.<br />|
|[Xml](Xml.md)|Actual data defining the databinding\.<br />|



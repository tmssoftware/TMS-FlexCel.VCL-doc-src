---
uid: TCryptographicAttributeObject
description: TCryptographicAttributeObject
---

# TCryptographicAttributeObject Class

An attribute that is signed together with the document, like the ESS signing\-certificate\-v2 attribute required by CAdES signatures\. It is a set of values sharing the same [Oid](Oid.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCryptographicAttributeObject = class(TObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new attribute without values\. Add them to [Values](Values.md)\.<br />|


## Properties

|Name|Description|
|---|---|
|[Oid](Oid.md)|Object identifier that says what this attribute is\.<br />|
|[Values](Values.md)|Values of this attribute\. All of them share the [Oid](Oid.md) of the attribute\.<br />|



---
uid: TAsnEncodedData
description: TAsnEncodedData
---

# TAsnEncodedData Record

A DER encoded value, together with the [TOid](../TOid/index.md) that says what the value means\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAsnEncodedData = record;</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TAsnEncodedData instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[Oid](Oid.md)|Object identifier that says what [RawData](RawData.md) means\.<br />|
|[RawData](RawData.md)|DER encoded value\.<br />|



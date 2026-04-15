---
uid: THeaderOrFooterAnchor
description: THeaderOrFooterAnchor
---

# THeaderOrFooterAnchor Record

Image information for an image inside a header or footer\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THeaderOrFooterAnchor = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Width](Width.md)|Width of the image in device independent pixels \(dip\)\. 1 dip = 1/96 inch, no matter the reslution of the output device\.<br />|
|[Height](Height.md)|Height of the image in device independent pixels \(dip\)\. 1 dip = 1/96 inch, no matter the reslution of the output device\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Anchor for a Header or footer image\.<br />|
|[GetData](GetData.md)|All the data as a byte array\.<br />|
|[Clone](Clone.md)|Returns a clone of the anchor\.<br />|
|[EqualValues](EqualValues.md)|Returns true if both instances of the objects contain the same values\. Instances might be different, this method will return if their values are equal\. Instances can be null\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Length](Length.md)|Length of the Serialized array\.<br />|



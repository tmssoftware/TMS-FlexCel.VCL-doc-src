---
uid: TColorChangeBlipTransform
description: TColorChangeBlipTransform
---

# TColorChangeBlipTransform Class

Represents a color transformation from one color to another\. This transform can be used to make a color transparent\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TColorChangeBlipTransform = class(<a href="../TBlipTransform/index.md">TBlipTransform</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new transform\.<br />|


## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Creates a deep copy of the object\.<br />|
|[CompareTo](CompareTo.md)|Compares two instances\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same contents\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[ColorFrom](ColorFrom.md)|Color which we are going to replace\.<br />|
|[ColorTo](ColorTo.md)|Color used to replace ColorFrom\.<br />|
|[UseAlpha](UseAlpha.md)|If false, the alpha components of ColorFrom and ColorTo will be ignored\.<br />|



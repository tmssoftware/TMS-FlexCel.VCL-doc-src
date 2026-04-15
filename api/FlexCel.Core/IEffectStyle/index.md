---
uid: IEffectStyle
description: IEffectStyle
---

# IEffectStyle Interface

A class encapsulating a style including 3D styles\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IEffectStyle = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[EnsureProperties](EnsureProperties.md)|If properties is null, it will create new empty properties\.<br />|
|[EnsureEffectLst](EnsureEffectLst.md)|If effects is null, it will create new empty effects\.<br />|
|[HasOuterShadowEffect](HasOuterShadowEffect.md)|Returns true if the effect has an outer shadow\.<br />|


## Properties

|Name|Description|
|---|---|
|[Scene3D](Scene3D.md)|Scene 3D effects\. Currently this is an xml string, in the future it might change to a parsed class\.<br />|
|[Shape3D](Shape3D.md)|Shape 3D effects\. Currently this is an xml string, in the future it might change to a parsed class\.<br />|
|[Properties](Properties.md)|2D effects applied to the shape\.<br />|



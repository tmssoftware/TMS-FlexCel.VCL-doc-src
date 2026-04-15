---
uid: IThemeFormatScheme
description: IThemeFormatScheme
---

# IThemeFormatScheme Interface

Represents the drawing formats \(fill styles, line styles, effects\) for a theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IThemeFormatScheme = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the format definition\. This will be shown in Excel UI\.<br />|
|[FillStyleList](FillStyleList.md)|This element defines a set of three fill styles that are used within a theme\.<br />|
|[LineStyleList](LineStyleList.md)|This element defines a list of three line styles for use within a theme\.<br />|
|[EffectStyleList](EffectStyleList.md)|This element defines a set of three effect styles \(or more\) that create the effect style list for a theme\.<br />|
|[BkFillStyleList](BkFillStyleList.md)|This element defines a list of background fills that are used within a theme\.<br />|



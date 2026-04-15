---
uid: IThemeColorScheme
description: IThemeColorScheme
---

# IThemeColorScheme Interface

A color scheme for a theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IThemeColorScheme = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Reset](Reset.md)|Resets the color scheme to be the Excel 2007 standard\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the color definition\. This will be shown in Excel UI\.<br />|
|[IsStandard2007](IsStandard2007.md)|True if this is the standard Excel 2007 color palette\.<br />|
|[Item\[const themeColor\]](Itemconst-themeColor.md)|Returns a color definition for a themed color\.<br />|



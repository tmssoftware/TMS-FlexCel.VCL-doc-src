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
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[Reset](Reset.md)|Resets the color scheme to be the Excel 2007 standard\.<br />|


## Properties

|Name|Description|
|---|---|
|[IsStandard2007](IsStandard2007.md)|True if this is the standard Excel 2007 color palette\.<br />|
|[Item\[const themeColor\]](Itemconst-themeColor.md)|Returns a color definition for a themed color\.<br />|
|[Name](Name.md)|Name of the color definition\. This will be shown in Excel UI\.<br />|



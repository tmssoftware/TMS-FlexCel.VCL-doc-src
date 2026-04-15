---
uid: IThemeElements
description: IThemeElements
---

# IThemeElements Interface

Definitions of the elements in a theme \(colors, fonts, formats\)\. This is the main part of a theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IThemeElements = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[IsStandard2007](IsStandard2007.md)|Returns true if the elements in this theme are the default ones in Office 2007\.<br />|
|[ColorScheme](ColorScheme.md)|Color Scheme in the theme\.<br />|
|[FontScheme](FontScheme.md)|Font Scheme in the theme\.<br />|
|[FormatScheme](FormatScheme.md)|Format Scheme \(Effects\)\. This won't affect cells in the spreadsheet, but can affect drawings\.<br />|



---
uid: ITheme
description: ITheme
---

# ITheme Interface

Contains a complete definition for an Office Theme\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ITheme = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[FileFormat](FileFormat.md)|Returns the file format normally associated with the theme\. Note that multiple Excel version can use the same theme, so this method will return the latest Excel using this theme\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the theme definition\. This will be shown in Excel UI\.<br />|
|[Elements](Elements.md)|Elements of the theme\.<br />|
|[ThemeVersion](ThemeVersion.md)|Excel version that saved this theme\. For Excel 2007 this value is 124226\. For themes new to Excel 2010, this value might be 144315\. Excel 2016 is 164011 and Excel 2019 is 166925|
|[IsStandard2007](IsStandard2007.md)|Returns true if the theme is standard as saved by Excel 2007\. Note that Excel versions bigger than 2010 use different standard themes\.<br />|



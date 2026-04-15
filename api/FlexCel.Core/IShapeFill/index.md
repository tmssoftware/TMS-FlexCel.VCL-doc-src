---
uid: IShapeFill
description: IShapeFill
---

# IShapeFill Interface

Contains the information for the fill of an autoshape\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IShapeFill = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|
|[GetFill](GetFill.md)|Fill style for this object\. This method will return [FillStyle](FillStyle.md) if it isn't null, or the default theme fill if it is\.<br />|


## Properties

|Name|Description|
|---|---|
|[HasFill](HasFill.md)|True if the object has fill, false if it is transparent\.<br />|
|[FillStyle](FillStyle.md)|Fill for the shape\. If this value is null, the fill specified in the theme will be used instead\.<br />To know the real fill style used even if this value is null, use [GetFill](GetFill.md)|
|[ThemeColor](ThemeColor.md)|Fill taken from a theme\. If [FillStyle](FillStyle.md) is null, this color here will be used along with the current theme\.<br />|
|[ThemeStyle](ThemeStyle.md)|Style \(subtle, normal, intense\) from the theme used, when a theme is used\.<br />|
|[UseThemeBk](UseThemeBk.md)|If true and using a theme, the background fill from the theme will be used, if not, the normal fill from the theme will be used\.<br />|



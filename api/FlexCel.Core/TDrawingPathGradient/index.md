---
uid: TDrawingPathGradient
description: TDrawingPathGradient
---

# TDrawingPathGradient Class

Holds a Path gradient definition\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingPathGradient = class(<a href="../TDrawingGradientDef/index.md">TDrawingGradientDef</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TDrawingPath object\.<br />|


## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if this instance has the same data as the object obj\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both objects are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for this object|


## Properties

|Name|Description|
|---|---|
|[FillToRect](FillToRect.md)|This element defines the "focus" rectangle for the center shade, specified relative to the fill tile rectangle\.<br /><br />The center shade fills the entire tile except the margins specified by each attribute\.<br /><br />Each edge of the center shade rectangle is defined by a percentage offset from the corresponding edge of the  tile rectangle\.  A positive percentage specifies an inset, while a negative percentage specifies an outset\.<br />|
|[Path](Path.md)|Specifies the shape of the path to follow\.<br />|



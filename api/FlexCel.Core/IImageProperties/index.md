---
uid: IImageProperties
description: IImageProperties
---

# IImageProperties Interface

Image information for a normal image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IImageProperties = interface(<a href="../IBaseImageProperties/index.md">IBaseImageProperties</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CreateShapeOptions](CreateShapeOptions.md)|Internal use, don't use directly;|
|[Dec](Dec.md)|Returns a COPY of the class with its coords decremented by 1\.<br />|
|[DecNoCopy](DecNoCopy.md)|Decrements the anchor of the image, and returns the SAME object\. This method doesn't clone the TImageProperties object\.<br />|
|[Inc](Inc.md)|Returns a COPY of the class with its coordinates incremented by 1\.<br />|
|[IncNoCopy](IncNoCopy.md)|Increments the anchor of the image, and returns the SAME object\. This method doesn't clone the TImageProperties object\.<br />|
|[ShapeOptions](ShapeOptions.md)|Internal use, don't use directly;|


## Properties

|Name|Description|
|---|---|
|[AltText](AltText.md)|Alternative Text\. This is the same as the "Alt Text" tab in the properties dialog for the image, and is used when exporting to HTML\.<br />|
|[Anchor](Anchor.md)|Image position|
|[IsCameraObject](IsCameraObject.md)|Returns true if this is a camera object|
|[ShapeName](ShapeName.md)|Name of the image\. It sets/gets the name of the shape for the image as you can see it on the names combobox\.<br />If you set it to null Excel will show a generic name, like "Picture 31"|
|[Title](Title.md)|Specifies the title \(caption\) of the current object\.<br />|



---
uid: IEmbeddedObjects
description: IEmbeddedObjects
---

# IEmbeddedObjects Interface

Use this interface to read or write Embedded drawing objects inside other object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IEmbeddedObjects = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetObjectProperties](GetObjectProperties.md)|Returns information on an object and all of its children\.<br />|
|[SetObjectText](SetObjectText.md)|**Overloaded<br />**  [SetObjectText\(Integer, string, string\)](SetObjectText.md#iembeddedobjectssetobjecttextinteger-string-string)<br />  [SetObjectText\(Integer, string, TRichString\)](SetObjectText.md#iembeddedobjectssetobjecttextinteger-string-trichstring)<br />  [SetObjectText\(Integer, string, TDrawingRichString\)](SetObjectText.md#iembeddedobjectssetobjecttextinteger-string-tdrawingrichstring)<br />|
|[DeleteObject](DeleteObject.md)|**Overloaded<br />**  [DeleteObject\(Integer\)](DeleteObject.md#iembeddedobjectsdeleteobjectinteger)<br />  [DeleteObject\(Integer, string\)](DeleteObject.md#iembeddedobjectsdeleteobjectinteger-string)<br />|
|[GetImage](GetImage.md)|Returns an image and its type\.<br />Note that for SVG images, xlsx files store both a PNG and SVG image\. In those cases, for backward compatibility reasons, this method will return the PNG image\. To get the SVG, call [GetImageAlternate](GetImageAlternate.md)|
|[HasImageAlternate](HasImageAlternate.md)|Returns true if the image has an alternate representation\. This currently happens only with SVG images, which have a PNG base and an SVG alternate\. If the image has an alternate, you can get the data with [GetImageAlternate](GetImageAlternate.md)|
|[GetImageAlternate](GetImageAlternate.md)|Returns an image and its type\. Currently this method is the same as [GetImage](GetImage.md) for all images except SVG\.<br />For SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [GetImage](GetImage.md)|
|[AddImageAlternate](AddImageAlternate.md)|Adds an image to the active sheet\.<br />Currently, this method is only needed for SVG images, since SVG images are stored as both PNG and SVG inside the xlsx file\. This method allows you to supply both images\.<br />|
|[GetImageProperties](GetImageProperties.md)|Returns image position and size\.<br />|
|[DeleteImage](DeleteImage.md)|Deletes the image at position imageIndex\.<br />|
|[GetShapeLinkedCell](GetShapeLinkedCell.md)|Returns the cell that is linked to the shape or image\. If the object isn't linked, this method will return null\.<br />Note that when you change the value in the cell linked to this object,  the value of the object will change\.<br />Also note that this method applies to shapes like a rectangle or circle, or an image\. Objects like a combobox  won't be reported by this method\.<br />|
|[SetShapeLinkedCell](SetShapeLinkedCell.md)|Links the shape or image to a cell, if the shape can be linked\. To unlink the cell, make linkedCell null\.<br />Note that this method applies to shapes like a rectangle or a circle, or an image, not to the link of a forms object like a combobox or a radiobutton\.<br />|
|[ImageIndexTo&#8203;Object&#8203;Path](ImageIndexToObjectPath.md)|Returns the absolute object path for an image, given an image index\. Note that this method can be slow if there are many objects in the file\.<br />Whenever possible, prefer the methods that take directly an imageIndex instead of converting the imageIndex to an objectPath\.<br />|


## Properties

|Name|Description|
|---|---|
|[ObjectCount](ObjectCount.md)|The number of objects that are embedded inside this object\.<br />|



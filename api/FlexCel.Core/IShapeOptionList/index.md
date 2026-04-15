---
uid: IShapeOptionList
description: IShapeOptionList
---

# IShapeOptionList Interface

This class holds a list of key/values pairs specifying the options for a shape\.
To Get a value from it, use: ShapeOptionList\[TShapeOption\.xxx\];

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IShapeOptionList = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[AsLong](AsLong.md)|Returns a long property if it exists, otherwise the default value\. Note: This method will always assume a positive number\.<br />To get a signed int, use [AsSignedLong](AsSignedLong.md)|
|[AsSignedLong](AsSignedLong.md)|Returns a long property if it exists, otherwise the default value\. Note: This method will return negative numbers if the number is bigger than 65536\.<br />To get an unsigned int, use [AsLong](AsLong.md)|
|[AsInt32](AsInt32.md)|Returns a long property if it exists, otherwise the default value\. Note: This method will return negative numbers if the number is bigger than 65536\.<br />|
|[AsUInt32](AsUInt32.md)|Returns a long property if it exists, otherwise the default value\. Note: This method will always return positive numbers\.<br />To get an signed int, use [AsInt32](AsInt32.md)|
|[As1616](As1616.md)|Returns a float \(Expressed as 16\.16\) property if it exists, otherwise the default value\.<br />|
|[AsBool](AsBool.md)|**Overloaded<br />**  [AsBool\(TShapeOption, Boolean\)](AsBool.md#ishapeoptionlistasbooltshapeoption-boolean)<br />  [AsBool\(TShapeOption, Boolean, Integer\)](AsBool.md#ishapeoptionlistasbooltshapeoption-boolean-integer)<br />|
|[AsUnicodeString](AsUnicodeString.md)|Returns an unicode property if it exists, otherwise the default value\.<br />|
|[AsByteArray](AsByteArray.md)|Returns a byte array property if it exists, otherwise null\.<br />|
|[GetGradientStopAlpha](GetGradientStopAlpha.md)|Returns a list of individual alpha values for the stops of a gradient\. This is not available in xls files, only xlsx\.<br />The alpha values determine the opacity of each stop, with 0 being completely transparent and 255 being completely opaque\.<br />This value might be null if there is no gradient in the pattern, or if the individual stops don't have a defined alpha\.<br />|
|[AsHyperLink](AsHyperLink.md)|**Overloaded<br />**  [AsHyperLink\(TShapeOption, TDrawingHyperlink\)](AsHyperLink.md#ishapeoptionlistashyperlinktshapeoption-tdrawinghyperlink)<br />  [AsHyperLink\(TCoreExcelFile, TShapeOption, TDrawingHyperlink\)](AsHyperLink.md#ishapeoptionlistashyperlinktcoreexcelfile-tshapeoption-tdrawinghyperlink)<br />|
|[Clone](Clone.md)|Creates a deep copy of the object\.<br />|
|[AsImage](AsImage.md)|Returns a byte array with the image if it exists, otherwise null\.<br />Note that for SVG images, xlsx files store both a PNG and SVG image\. In those cases, for backward compatibility reasons, this method will return the PNG image\. To get the SVG, call [AsImageAlternate](AsImageAlternate.md)|
|[AsImageAlternate](AsImageAlternate.md)|Returns a byte array with the image if it exists, otherwise null\.<br />Note that for SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [AsImage](AsImage.md)|
|[SetValue](SetValue.md)|**Overloaded<br />**  [SetValue\(TShapeOption, Double\)](SetValue.md#ishapeoptionlistsetvaluetshapeoption-double)<br />  [SetValue\(TShapeOption, Boolean\)](SetValue.md#ishapeoptionlistsetvaluetshapeoption-boolean)<br />  [SetValue\(TShapeOption, TDrawingHyperlink\)](SetValue.md#ishapeoptionlistsetvaluetshapeoption-tdrawinghyperlink)<br />  [SetValue\(TShapeOption, string\)](SetValue.md#ishapeoptionlistsetvaluetshapeoption-string)<br />|
|[SetImage](SetImage.md)|Sets a property with the bytes of an image\.<br />|
|[SetBytes](SetBytes.md)|Sets a property with arbitrary bytes\.<br />|


## Properties

|Name|Description|
|---|---|
|[Item\[const key\]](Itemconst-key.md)|Gets the value for a key\. Value can be a long or a string, depending on the type of property\.<br />|



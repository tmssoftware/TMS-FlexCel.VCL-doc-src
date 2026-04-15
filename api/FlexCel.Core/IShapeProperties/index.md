---
uid: IShapeProperties
description: IShapeProperties
---

# IShapeProperties Interface

A class describing an Excel graphics object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IShapeProperties = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[TextAsRichString](TextAsRichString.md)|Converts the TDrawingRichString to a TRichString|
|[Children](Children.md)|Returns one of the shapes inside of this one\.<br />|
|[AddChild](AddChild.md)|Adds a new child for this autoshape\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[GetAlternateText](GetAlternateText.md)|Returns the Alternate Text for a shape\. This is used for example in the "Alt" attribute when exporting to html\.<br />Note that if there is no alternate text for the image \(&#8203;TShape&#8203;Option\.&#8203;wzDescription\)&#8203;, this method will return the image name\.<br />The idea is to return something that can describe the image for users who can't see them\.<br />|
|[HasShadow](HasShadow.md)|Returns true if the shape has a shadow\.<br />|


## Properties

|Name|Description|
|---|---|
|[ShapeType](ShapeType.md)|Type of shape\. Note that this is not the same as [ObjectType](ObjectType.md) A comment might have a ShapeType=&#8203;TShape&#8203;Type\.&#8203;Rectangle, but its object type is TObjectType\.&#8203;Comment\.&#8203;<br />A rectangle Autoshape will also have ShapeType=&#8203;TShape&#8203;Type\.&#8203;Rectangle, but its ObjectType will be TObjectType\.&#8203;Rectangle\.&#8203;<br />|
|[ObjectType](ObjectType.md)|Type of object\. Note that this is not the same as [ShapeType](ShapeType.md)\.<br />A comment might have a ShapeType = TShapeType\.&#8203;Rectangle, but its object type is TObjectType\.&#8203;Comment\.&#8203;<br />A rectangle Autoshape will also have ShapeType=&#8203;TShape&#8203;Type\.&#8203;Rectangle, but its ObjectType will be TObjectType\.&#8203;Rectangle\.&#8203;<br />|
|[ShapeName](ShapeName.md)|Name of the shape if it is named, null otherwise\.<br />|
|[ShapeId](ShapeId.md)|This is an internal identified for the shape\. It will remain the same once the file is loaded, but it might change when you load the same file at different times\.<br />|
|[ObjectPath](ObjectPath.md)|Use this string to identify the shape when it is not the first on the hierarchy\.<br />For Example, imagine you have a Group Shape A with 2 children, B and C\.<br />If you want to change the text on shape C, you need to call SetObjectText\(&#8203;n,&#8203;Object&#8203;Path\)&#8203;;<br />The object path can be of 2 types: Absolute or relative\. Absolute object paths start with "\\" and include the parent object\. Relative paths don't include the main group shape\.<br /><br />For example the absolute path "\\1\\2\\3" is the same as accessing the object 1, with object path "2\\3"[...[more]](ObjectPath.md)|
|[ObjectPathAbsolute](ObjectPathAbsolute.md)|Use this string to identify the shape when it is not the first on the hierarchy\.<br />For Example, imagine you have a Group Shape A with 2 children, B and C\.<br />If you want to change the text on shape C, you need to call SetObjectText\(n, ObjectPath\);<br />The object path can be of 2 types: Absolute or relative\. Absolute object paths start with "\\" and include the parent object\. Relative paths don't include the main group shape\.<br /><br />For example the absolute path "\\1\\2\\3" is the same as accessing the object 1, with object path "2\\3"[...[more]](ObjectPathAbsolute.md)|
|[ObjectPathShapeId](ObjectPathShapeId.md)|Returns the object path as a shape id\. This is used mostly internally\.<br />|
|[Text](Text.md)|Text of the shape if is has some, null otherwise\.<br />|
|[TextFlags](TextFlags.md)|Option flags for the Text shape\.<br />**Important:**Instead of changing this flag, you should use instead [LockText](LockText.md), [TextHorizontal&#8203;Alignment](TextHorizontalAlignment.md) and  [TextVertical&#8203;Alignment](TextVerticalAlignment.md)\. Changing those properties will automatically change the text flags, but in a simpler way\.<br /><br /><br />The option flags work differently in xls and xlsx files\. All properties in FlexCel assume the xls way, and convert to the corresponding properties in xlsx when saving or loading xlsx files\. For more information, check[...[more]](TextFlags.md)|
|[TextHorizontal&#8203;Alignment](TextHorizontalAlignment.md)|This property gets or sets the horizontal alignment for the text\.<br /><br /><br />Note that xls and xlsx files behave differently when text is rotated with [TextRotated](TextRotated.md)\.<br />In xlsx, if you rotate the text 90 degrees clockwise, a text aligned to the top and left will be aligned to the top and right of the shape\. While in xls, the rotation is absolute and always means aligned to the top left of the shape\.<br /><br /><br />This method uses the xls way, even when dealing with xlsx files\. For more information see[...[more]](TextHorizontalAlignment.md)|
|[TextVertical&#8203;Alignment](TextVerticalAlignment.md)|This property gets or sets the vertical alignment for the text\.<br /><br /><br />Note that xls and xlsx files behave differently when text is rotated with [TextRotated](TextRotated.md)\.<br />In xlsx, if you rotate the text 90 degrees clockwise, a text aligned to the top and left will be aligned to the top and right of the shape\. While in xls, the rotation is absolute and always means aligned to the top left of the shape\.<br /><br /><br />This method uses the xls way, even when dealing with xlsx files\. For more information see[...[more]](TextVerticalAlignment.md)|
|[LockText](LockText.md)|True if the Lock Text option is on \(Format Text Box dialog box, Protection tab\)\. When changing this property, the value of [TextFlags](TextFlags.md), will change too\.<br />|
|[TextRotation](TextRotation.md)|Text rotation: 0 means horizontal, 1 means vertical text, 2 means rotated \-90 degrees clockwise, 3 means rotated 90 degrees clockwise\.<br />This method uses the xls way to set text rotation\.<br /><br /><br />For more information, see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)|
|[TextRotated](TextRotated.md)|This methods gets or sets [TextRotation](TextRotation.md) in a simpler way\. As with all FlexCel methods, it uses the xls, not the xlsx way to apply the rotation\.<br /><br />For more information, see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)\.<br />|
|[RotateTextWithShape](RotateTextWithShape.md)|If true, the text will be rotated with the shape\. Note that this option is only available in Excel 2007 or newer\.<br />Older Excels will never rotate the text with the shape\.<br />|
|[TextVerticalOverflow](TextVerticalOverflow.md)|Gets or sets how the text overflows the shape vertically\. Note that the checkbox in Excel "Allow text to overflow shape" sets both this property and [TextHorizontal&#8203;Overflow](TextHorizontalOverflow.md)|
|[TextHorizontal&#8203;Overflow](TextHorizontalOverflow.md)|Gets or sets how the text overflows the shape horizontally\. Note that the checkbox in Excel "Allow text to overflow shape" sets both this property and [TextVerticalOverflow](TextVerticalOverflow.md)|
|[ShapeOptions](ShapeOptions.md)|A lot of personalized settings, like shadow type fill color, line type, etc\.<br />|
|[Anchor](Anchor.md)|Coordinates of the shape\. Note that when the shape is a group, this value is null and the real anchor is  returned in the first child of the shape\.<br />To get the real Anchor of a first level object, use [NestedAnchor](NestedAnchor.md)|
|[XlsxChartAnchor](XlsxChartAnchor.md)|If the chart is inside a chart, this member can hold more exact information than [Anchor](Anchor.md)\.<br />|
|[ShapeGeom](ShapeGeom.md)|Geometry of the shape, if it is an xlsx shape\. Shapes in xls will have this value null\.<br />This property contains a parsed ShapeGeometry and it is used instead if it exists\.<br />|
|[ShapeGeometry](ShapeGeometry.md)|Geometry of the shape as XML, if it is an xlsx shape\. Shapes in xls will have this value empty\.<br />You can find the XML string by creating the shape in Excel and opening the file with APIMate\.<br />|
|[ShapeFill](ShapeFill.md)|Fill of the shape, for xlsx shapes \(even those which are saved in xls files\)\. This property has a more complete description of the fill style than the one you can get by querying [ShapeOptions](ShapeOptions.md), but will be null for xls files saved by Excel 2003 or earlier\.<br />|
|[ShapeLine](ShapeLine.md)|Line of the shape, for xlsx shapes \(even those which are saved in xls files\)\. This property has a more complete description of the line style than the one you can get by querying [ShapeOptions](ShapeOptions.md), but will be null for xls files saved by Excel 2003 or earlier\.<br />|
|[ShapeEffects](ShapeEffects.md)|Effects for the shape, for xlsx shapes \(even those which are saved in xls files\)\. The effects include glow, shadow, etc\.<br />|
|[ShapeThemeEffects](ShapeThemeEffects.md)|Returns the theme effects applied to the shape\.<br />|
|[ShapeThemeFont](ShapeThemeFont.md)|Theme Font used for the text in the shape\. This property only affects xlsx files, in xls files the font is always arial black\.<br />You can change the font only inside the rich string, not in a global way\. In xls files this will be null\.<br />|
|[NestedOptions](NestedOptions.md)|When the shape is a group, the real properties of the shape are in its first children\. This method  returns the correct shape options\.<br />|
|[NestedAnchor](NestedAnchor.md)|Real Coordinates of the shape\. Note that when the shape is a group, the value in [Anchor](Anchor.md) is null and the real anchor is  returned in the first child of the shape\.<br />This method will get the real Anchor of a first level object\.<br />|
|[FlipH](FlipH.md)|True if the shape is flipped horizontally\.<br />|
|[FlipV](FlipV.md)|True if the shape is flipped vertically\.<br />|
|[IsConnector](IsConnector.md)|True if the shape is a connector\.<br />|
|[StartShapeConnection](StartShapeConnection.md)|This property only applies to connector shapes\. It identifies the first shape where the connector is attached to\.<br />|
|[EndShapeConnection](EndShapeConnection.md)|This property only applies to connector shapes\. It identifies the second shape where the connector is attached to\.<br />|
|[Print](Print.md)|True if the shape should be printed\.<br />|
|[IsPrintable](IsPrintable.md)|True if the shape should be printed\. Different from [Print](Print.md), this property also looks inside groups\.<br />If the shape is a group container, it will return whether the group is printable, not if the container is\.<br />|
|[IsLocked](IsLocked.md)|True if the shape is locked\.<br />|
|[Visible](Visible.md)|True if the shape is visible\.<br />|
|[IsActiveX](IsActiveX.md)|Returns true if the object is an ActiveX object\.<br />|
|[IsOleObject](IsOleObject.md)|Returns true if the object is an embedded ole object\.<br />|
|[IsInternal](IsInternal.md)|Returns true if the object is an internal object, like a comment or the arrow of an autofilter\.<br />Internal objects shouldn't be modified\.<br />|
|[ChildrenCount](ChildrenCount.md)|Number of shapes that are inside this shape\.<br />|



---
uid: TImageInformationEventArgs
description: TImageInformationEventArgs
---

# TImageInformationEventArgs Class

Arguments passed on [TFlexCelHtmlExport.OnGetImageInformation](../TFlexCelHtmlExport/OnGetImageInformation.md),

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TImageInformationEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|ExcelFile with the image, positioned in the sheet that we are rendering\.<br />Make sure if you modify ActiveSheet of this instance to restore it back to the original value before exiting the event\.<br />|
|[ObjectIndex](ObjectIndex.md)|Object index of the object being rendered\. You can use xls\.&#8203;Get&#8203;Object\(&#8203;object&#8203;Index\) to get the object properties, or you can use this property to attach an unique number in the sheet to the image filename\. If the image is not an object \(for example it is a rotated text\) this property will be \-1\.<br />|
|[ShapeProps](ShapeProps.md)|Shape properties of the object being rendered\. You can use them to get the name of the object, its size, etc\.<br />If the image is not an object \(for example it is a rotated text\) this property will be null\.<br />|
|[ImageStream](ImageStream.md)|The stream where the images will be saved\. Keep it null to store the image as a file using [ImageFile](ImageFile.md)\.<br />When saving as MHTML this parameter does nothing, since all images will be saved in the same MTHML stream\.<br />|
|[ImageFile](ImageFile.md)|The file where the image will be saved\. If [ImageStream](ImageStream.md) is not null, this property will do nothing\.<br />If both this property and [ImageStream](ImageStream.md) are null, the image will not be saved\.<br />When saving as MHTML this parameter does nothing, since all images will be saved in the same MTHML stream\.<br />|
|[ImageLink](ImageLink.md)|The link that will be inserted in the html file\. Change it if you change the default image location\.<br />Set it to null to not add a link to this image in the generated html file\. If you want to avoid exporting all images, you can use [THidePrintObjects](../../FlexCel.Core/THidePrintObjects.md) for that\. But if you just want to avoid exporting one image in a file, you can do it by setting [ImageStream](ImageStream.md), [ImageFile](ImageFile.md) and this property to null\.<br />|
|[ImageLinkNeeds&#8203;Escaping](ImageLinkNeedsEscaping.md)|If true \(the default\) the link you provide in [ImageLink](ImageLink.md) is not escaped and will be escaped by FlexCel\.<br />So for example, the link "http://my site" will be escaped to "http:&#8203;//&#8203;my%&#8203;%20site"&#8203;\.&#8203;<br />If the link you provided was already escaped, then set this variable to false\.<br />|
|[AlternateText](AlternateText.md)|Alternate text for the image, to show in the "ALT" tag when a browser cannot display images\.<br />By default this is set to the text in the box "Alternative Text" in the web tab on the image properties\.<br />If no Alternative text is supplied in the file, the image name will be used here\.<br />|
|[HyperLink](HyperLink.md)|Hyperlink where the image will point to\. This is automatically read from the image hyperlink if it has one, but you can modify, delete or add a new hyperlink for any image with this property\.<br />|
|[HyperLinkTitle](HyperLinkTitle.md)|Hyperlink title if the image has an hyperlink\.<br />|
|[SavedImageFormat](SavedImageFormat.md)|File format in which to save this image\. Do not modify it to keep the default format\.<br />**Important:** If you want to render the charts as SVG objects instead of PNG bitmaps, you need to set this property to THtmlImageFormat\.&#8203;Svg\.&#8203;<br />|



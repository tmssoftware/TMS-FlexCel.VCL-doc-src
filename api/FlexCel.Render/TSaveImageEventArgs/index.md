---
uid: TSaveImageEventArgs
description: TSaveImageEventArgs
---

# TSaveImageEventArgs Class

Arguments passed on [TFlexCelHtmlExport.OnSaveImage](../TFlexCelHtmlExport/OnSaveImage.md),

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TSaveImageEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|ExcelFile with the image, positioned in the sheet that we are rendering\.<br />Make sure if you modify ActiveSheet of this instance to restore it back to the original value before exiting the event\.<br />|
|[ObjectIndex](ObjectIndex.md)|Object index of the object being rendered\. You can use xls\.&#8203;Get&#8203;Object\(&#8203;object&#8203;Index\) to get the object properties\.<br />If the image is not an object \(for example it is a rotated text\) this property will be \-1\.<br />|
|[ShapeProps](ShapeProps.md)|Shape properties of the object being rendered\. You can use them to get the name of the object, its size, etc\.<br />If the image is not an object \(for example it is a rotated text\) this property will be null\.<br />|
|[ImageFile](ImageFile.md)|The file where the image is expected to be saved\.<br />|
|[ImageLink](ImageLink.md)|The link that will be inserted in the html file\.<br />|
|[AlternateText](AlternateText.md)|Alternate text for the image, to show in the "ALT" tag when a browser cannot display images\.<br />By default this is set to the text in the box "Alternative Text" in the web tab on the image properties\.<br />If no Alternative text is supplied in the file, the image name will be used here\.<br />|
|[SavedImageFormat](SavedImageFormat.md)|File format in which the image is\.<br />|
|[ImageToSave](ImageToSave.md)|Image that will be saved\. You can use it to save it yourself\.<br />Note that when saving as SVG, this will be null\.<br />|
|[Processed](Processed.md)|Set this property to true if you have taken care of saving the image, and FlexCel does not need to save it\.<br />If you just used this event to get information on the image being saved, but would like to keep the normal flux, set it to false\.<br />|



---
uid: TPartialExportState
description: TPartialExportState
---

# TPartialExportState Class

This class is used to save the necessary information to partially export a file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TPartialExportState = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of TPartialExport&#8203;State\.&#8203;<br />|


## Methods

|Name|Description|
|---|---|
|[SaveCss](SaveCss.md)|**Overloaded<br />**  [SaveCss\(TFlexCelWriter\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter)<br />  [SaveCss\(TFlexCelWriter, Boolean\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter-boolean)<br />|
|[SaveRelevantHeaders](SaveRelevantHeaders.md)|This method is a middle ground between [SaveCss\(&#8203;&#8203;TFlexCel&#8203;Writer\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter) and [SaveFullHeaders](SaveFullHeaders.md)\.<br />It will output only the headers that you need to add to an existing HTML file in order to include the body in the body part\.<br />This means that the tags like \<html> are not included\.<br />|
|[SaveFullHeaders](SaveFullHeaders.md)|This method will output the full HTML headers needed to create an HTML file with the information in this object\.<br />If you wish to mix the output of the file with existing headers, you can use [SaveRelevantHeaders](SaveRelevantHeaders.md) instead to get only the relevant information to mix in the headers, or [SaveCss\(&#8203;&#8203;TFlexCel&#8203;Writer\)](SaveCss.md#tpartialexportstatesavecsstflexcelwriter) to get only the CSS classes that need to be put in the header\.<br />|
|[StartBody](StartBody.md)|Starts writing a body declaration\. After calling this method, you should call [SaveBody](SaveBody.md) for the parts you want to save, and end up with a call to [EndHtmlFile](EndHtmlFile.md)|
|[EndHtmlFile](EndHtmlFile.md)|Writes the "\</body>" end tag in the html file and the head/html end tags\. It also finalizes the parts when saving to MHTML\.<br />|
|[SaveBody](SaveBody.md)|Use this method to output the body information on this object to an HTML page\.<br />|
|[GetImage](GetImage.md)|Returns one of the images for one of the saved sheets\.<br />|


## Properties

|Name|Description|
|---|---|
|[BodyCount](BodyCount.md)|Number of parts added to this object\.<br />|



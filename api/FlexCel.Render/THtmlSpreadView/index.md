---
uid: THtmlSpreadView
description: THtmlSpreadView
---

# THtmlSpreadView Class

The properties in this class make the generated file look more like when you view a Spreadsheet in Excel, and less like a printed page\. By default, FlexCel tries to mimic the printed\-page output, not the interactive view\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">THtmlSpreadView = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance of THtmlSpreadView\.<br />|


## Properties

|Name|Description|
|---|---|
|[UseViewGridLines&#8203;AndHeadings](UseViewGridLinesAndHeadings.md)|By default, FlexCel will use the settings for gridlines and headings that apply to the printed page\.<br />If you set this property to true, it will use the settings for the interactive view\.<br />|
|[IgnorePrintAreas](IgnorePrintAreas.md)|If true, we will use the maximum visible column and row in the spreadsheet, ignoring any print area that might be set in the sheet\. This will make the generated file look more like the interactive view in Excel, and not like what the printed page would look like\.<br />|
|[HotTrack](HotTrack.md)|You can set the properties inside so the cells will highlight when the mouse is over them\.<br />Note that tracking the columns will increase the size of the generated file\. On the ohter hand, tracking the rows and cells will not increase the file size\.<br />No javascript is used for the tracking, only CSS\.<br />|



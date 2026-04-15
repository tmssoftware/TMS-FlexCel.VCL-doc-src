---
uid: TGetFontFolderEventArgs
description: TGetFontFolderEventArgs
---

# TGetFontFolderEventArgs Class

Arguments passed on [TFlexCelPdfExport.GetFontFolder](../../FlexCel.Render/TFlexCelPdfExport/GetFontFolder.md)\.
Use this event to provide font information for embedding\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TGetFontFolderEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[FontPath](FontPath.md)|Return here the font path to the "Fonts" folder where ttf files are located\.<br /><br />FlexCel will search in the folder you return here, and in \*\*all subfolders\*\* of that folder for ttf files\.<br /><br /><br />In Android, we use a "@folder" syntax to refer to assets\. So for example to specify that the fonts are in the "fonts" folder asset, return "@fonts" here\. If the fonts are in a normal folder, just return the folder\.<br /><br /><br /><br />You can return more than one folder here, separating them with semicolons \(;\)\. So you could for example return the string 'c:&#8203;\\font1folder;&#8203;c:&#8203;\\font2folder' and FlexCel will search inside font1folder and font2folder\.<br />[...[more]](FontPath.md)|
|[Applied](Applied.md)|Set Applied = false if the font is not being processed by the event, and FlexCel should try to find the font path for the font as if the event wasn't assigned\.<br />|
|[InputFont](InputFont.md)|The font for which you need to return the data\.<br />|



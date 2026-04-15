---
uid: TSheetSelectorEntryEventArgs
description: TSheetSelectorEntryEventArgs
---

# TSheetSelectorEntryEventArgs Class

Arguments passed on FlexCel\.Render\.TStandardSheetSelector\.OnSheetSelectorEntry\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TSheetSelectorEntryEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|ExcelFile we are drawing the sheet selector in, positioned in the sheet that we are rendering\.<br />Make sure if you modify ActiveSheet of this instance to restore it back to the original value before exiting the event\.<br />|
|[ActiveSheet](ActiveSheet.md)|Sheet index of the entry\. This is equivalent to [Workbook](Workbook.md)\.ActiveSheet|
|[RenderingSheet](RenderingSheet.md)|Sheet we are currently rendering\. You can compare if \(RenderingSheet == ActiveSheet\) to highlight the active sheet when drawing the selector\.<br />|
|[Link](Link.md)|Place where this entry should link to\.<br />|
|[EntryText](EntryText.md)|Text that will be written in this cell of the selector\.<br />|
|[LinkNeedsEscaping](LinkNeedsEscaping.md)|If true \(the default\) the link you provide in [Link](Link.md) is not escaped and will be escaped by FlexCel\.<br />So for example, the link "http://my site" will be escaped to "http:&#8203;//&#8203;my%&#8203;%20site"&#8203;\.&#8203;<br />If the link you provided was already escaped, then set this variable to false\.<br />|



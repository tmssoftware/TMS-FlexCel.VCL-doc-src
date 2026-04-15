---
uid: THtmlHotTrack
description: THtmlHotTrack
---

# THtmlHotTrack Class

Defines how and if the cells will be highlighted when the mouse is over them\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">THtmlHotTrack = class(TFlexCelObject);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Enabled](Enabled.md)|Sets if the tracking is enabled or not\.<br />|
|[CellStyle](CellStyle.md)|Style to apply to the cell when the mouse is over it\. You can use any css style here\.<br />Set it to empty if you don't want to highlight the cells\.<br />|
|[RowHeadingStyle](RowHeadingStyle.md)|Style to apply to the heading rows when the mouse is over a cell\. You can use any css style here\.<br />Set it to empty if you don't want to highlight the headings\.<br /><br /><br />Note that this style only applies for left\-to\-right sheets\. To modify the style for right\-to\-left sheets, use [RowHeadingStyleRTL](RowHeadingStyleRTL.md)\.<br /><br />|
|[RowHeadingStyleRTL](RowHeadingStyleRTL.md)|Style to apply to the heading rows when in Right\-To\-Left \(RTL\) mode, when the mouse is over a cell\. You can use any css style here\.<br />Set it to empty if you don't want to highlight the headings\. RTL row headings have the line marker at the left, not the right\.<br />|
|[ColHeadingStyle](ColHeadingStyle.md)|Style to apply to the heading columns when the mouse is over a cell\. You can use any css style here\.<br />Set it to empty if you don't want to highlight the headings\. Note that highlighting the columns will increase the size of the generated file, so leave this one empty if you want to minimize the file size\.<br />Row and cell hot\-track won't increase the file size\.<br />|



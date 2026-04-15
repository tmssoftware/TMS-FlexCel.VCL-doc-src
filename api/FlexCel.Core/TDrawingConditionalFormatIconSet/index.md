---
uid: TDrawingConditionalFormatIconSet
description: TDrawingConditionalFormatIconSet
---

# TDrawingConditionalFormatIconSet Record

Defines the characteristics of a conditional format icon which is going to be rendered on the screen or to a file\.
It is used for exporting xls/x files to drawings or pdf\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingConditionalFormatIconSet = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new struct and initializes the data\.<br />|


## Properties

|Name|Description|
|---|---|
|[HasIcon](HasIcon.md)|If false, the cell doesn't have an icon\. Note that a cell that doesn't have an icon is different from a cell with a TCondFmtIcon&#8203;Set\.&#8203;None: The second case can be a custom icon set of noicon, and when rendering the cell we need to add an indentation to make room for the empty icon\. If HasIcon is false, no indentation in the text is needed\.<br />|
|[HideValues](HideValues.md)|If true, the contents of the cell won't be displayed\.<br />|
|[Icon](Icon.md)|Icon that must be rendered\. It only makes sense if [HasIcon](HasIcon.md) is true\.<br />|



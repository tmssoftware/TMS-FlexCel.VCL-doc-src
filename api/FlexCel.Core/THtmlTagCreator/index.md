---
uid: THtmlTagCreator
description: THtmlTagCreator
---

# THtmlTagCreator Record

Creates html tags for different actions, and depending on the HTML style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THtmlTagCreator = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[DiffFont](DiffFont.md)|Returns the tags for a difference between one font and the next\.<br />|
|[StartFontColor](StartFontColor.md)|Returns a tag to change the font color\. Remember to close it with [EndFontColor](EndFontColor.md)|
|[EndFontColor](EndFontColor.md)|Returns a tag to end changing a font color that was started with [StartFontColor](StartFontColor.md)|



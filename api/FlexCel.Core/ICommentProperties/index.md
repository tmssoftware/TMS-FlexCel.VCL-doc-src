---
uid: ICommentProperties
description: ICommentProperties
---

# ICommentProperties Interface

Holds the properties for a comment\. This class is a descendant of [IObjectProperties](../IObjectProperties/index.md), and it adds specific behavior for a comment\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ICommentProperties = interface(<a href="../IObjectProperties/index.md">IObjectProperties</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[TextProperties](TextProperties.md)|Properties of the text in the object\.<br />|
|[AutoSize](AutoSize.md)|If true, the comment box will adapt its size to the size of the text\.<br />|
|[Hidden](Hidden.md)|If true, the comment box will be hidden \(this is the default\)\.<br />|
|[AutoTextMargins](AutoTextMargins.md)|If true, the comment will use automatic margins around the text, instead of what is set in [TShapeOption.&#8203;dxText&#8203;Left](../TShapeOption.md), [TShapeOption.&#8203;dxText&#8203;Right](../TShapeOption.md), [TShapeOption.&#8203;dyTextTop](../TShapeOption.md) and [TShapeOption.&#8203;dyText&#8203;Bottom](../TShapeOption.md)\.<br />By default comments have automatic margins\.<br />|



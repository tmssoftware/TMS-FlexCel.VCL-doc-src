---
uid: TPdfCommentProperties
description: TPdfCommentProperties
---

# TPdfCommentProperties Record

Properties for a PDF comment\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfCommentProperties = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TPdfCommentProperties\)](Create.md#tpdfcommentpropertiescreatetpdfcommentproperties)<br />  [Create\(TPdfCommentType, TPdfCommentIcon, Double, TUIColor, TUIColor\)](Create.md#tpdfcommentpropertiescreatetpdfcommenttype-tpdfcommenticon-double-tuicolor-tuicolor)<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[CommentType](CommentType.md)|Type of comment\.<br />|
|[Icon](Icon.md)|Icon for the comment\. Only visible if [CommentType](CommentType.md) is Text|
|[Opacity](Opacity.md)|A value between 0 and 1 specifying the opacity of the note\.<br />|
|[BackgroundColor](BackgroundColor.md)|Background color for the comment\. Only visible if [CommentType](CommentType.md) is NOT Text|
|[LineColor](LineColor.md)|Line color for the comment\. Only visible if [CommentType](CommentType.md) is NOT Text|



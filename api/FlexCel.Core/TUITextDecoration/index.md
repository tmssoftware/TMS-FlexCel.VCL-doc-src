---
uid: TUITextDecoration
description: TUITextDecoration
---

# TUITextDecoration Record

Defines appearance of decorative lines used in text, like underline or strikeout\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUITextDecoration = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TUIUnderline\)](Create.md#tuitextdecorationcreatetuiunderline)<br />  [Create\(TUIStrikeout\)](Create.md#tuitextdecorationcreatetuistrikeout)<br />  [Create\(TUIUnderline, TUIStrikeout\)](Create.md#tuitextdecorationcreatetuiunderline-tuistrikeout)<br />|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[WithUnderline](WithUnderline.md)|Returns a copy of the record with a different underline\.<br />|
|[WithStrikeout](WithStrikeout.md)|Returns a copy of the record with a different strikeout\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Underline](Underline.md)|Defines the style of text underlining\.<br />|
|[Strikeout](Strikeout.md)|Defines the style of text strikeout\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the structure has no underline or strikeout\.<br />|



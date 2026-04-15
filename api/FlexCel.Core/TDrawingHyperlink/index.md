---
uid: TDrawingHyperlink
description: TDrawingHyperlink
---

# TDrawingHyperlink Record

Specifies an hyperlink in a drawing\. While this class is similar to THyperlink for links in cells, it has some differences\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingHyperlink = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tdrawinghyperlinkcreate)<br />  [Create\(string, string, string, string, Boolean, Boolean, Boolean\)](Create.md#tdrawinghyperlinkcreatestring-string-string-string-boolean-boolean-boolean)<br />  [Create\(string, string, string, string, string, Boolean, Boolean, Boolean\)](Create.md#tdrawinghyperlinkcreatestring-string-string-string-string-boolean-boolean-boolean)<br />|
|[Null](Null.md)|Returns an empty instance\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1, 0 or 1 depending if this object is smaller or bigger than the other\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same data\.<br />|
|[CloneLink](CloneLink.md)|Returns a deep clone of source\.<br />|
|[GetLinkType](GetLinkType.md)|Returns the type of hyperlink\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from TDrawingHyperlink to THyperLink](op_Implicit.md#implicit-conversion-from-tdrawinghyperlink-to-thyperlink)<br />  [Implicit conversion from THyperLink to TDrawingHyperlink](op_Implicit.md#implicit-conversion-from-thyperlink-to-tdrawinghyperlink)<br />  [Implicit conversion from TNull to TDrawingHyperlink](op_Implicit.md#implicit-conversion-from-tnull-to-tdrawinghyperlink)<br />|


## Properties

|Name|Description|
|---|---|
|[Url](Url.md)|Url for the link \(including the prefix like "file:///"\)\. Note that if the file has a [BaseUrl](BaseUrl.md), the final URL is given by [FullUrl](FullUrl.md)|
|[BaseUrl](BaseUrl.md)|Base URL that will be added to the start of [Url](Url.md) if it is set in the file\. The property [FullUrl](FullUrl.md) contains the combined URL\.<br />|
|[FullUrl](FullUrl.md)|Returns [BaseUrl](BaseUrl.md) combined with [Url](Url.md) when Url is not an absolute Uri\.<br />|
|[TargetFrame](TargetFrame.md)|If blank then a new window will be used\.|
|[Hint](Hint.md)|Tooltip to show when the user hovers over the hyperlink\.|
|[Action](Action.md)|Specifies an action that is to be taken when this hyperlink is activated\. This can be used to specify a slide to be navigated to or a script of code to be run\. Doesn't seem to be used in Excel\.|
|[HighlightClick](HighlightClick.md)|When set to true, the link will be painted in a "Visited" color\.|
|[AddToHistory](AddToHistory.md)|If true, the link will be added to the history\.|
|[EndsSounds](EndsSounds.md)|If true, any sound currently playing will be stopped when you click the link\.|



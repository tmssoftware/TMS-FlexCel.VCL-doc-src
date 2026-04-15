---
uid: THyperLink
description: THyperLink
---

# THyperLink Record

An encapsulation of an Excel hyperlink\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">THyperLink = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#thyperlinkcreate)<br />  [Create\(string, string, string, string\)](Create.md#thyperlinkcreatestring-string-string-string)<br />  [Create\(THyperLinkType, string, string, string, string\)](Create.md#thyperlinkcreatethyperlinktype-string-string-string-string)<br />  [Create\(THyperLinkType, string, string, string, string, string\)](Create.md#thyperlinkcreatethyperlinktype-string-string-string-string-string)<br />  [Create\(THyperLinkType, string, string, string, string, string, string\)](Create.md#thyperlinkcreatethyperlinktype-string-string-string-string-string-string)<br />|
|[Null](Null.md)|Creates an empty instance of an Hyperlink class\.<br />|
|[ToString](ToString.md)|Returns the text and description of the link\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[LinkType](LinkType.md)|The type of hyperlink: to a local file, to a url, to a cell or to a networked file\.<br />|
|[Text](Text.md)|Text of the HyperLink\. This is empty when linking to a cell\.<br />|
|[BaseUrl](BaseUrl.md)|Base Url that must be combined with Text\. This only happens if the file has a LinkBase property set\.<br />|
|[FullUrl](FullUrl.md)|Returns [BaseUrl](BaseUrl.md) combined with [Text](Text.md) when Text is not an absolute Uri\.<br />|
|[Description](Description.md)|Description of the HyperLink\.<br />|
|[TargetFrame](TargetFrame.md)|This parameter is not documented\. You will probably leave it empty\.<br />|
|[TextMark](TextMark.md)|When entering a URL, you can enter additional text following the url with a "\#" character \(for example www\.&#8203;your\_&#8203;url\.&#8203;com\#&#8203;myurl"&#8203;\) The text Mark is the text after the "\#" char\. When entering an address to a cell, the address goes here too\.<br />|
|[Hint](Hint.md)|Hint when the mouse hovers over the hyperlink\.<br />|



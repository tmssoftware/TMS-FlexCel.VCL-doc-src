---
uid: THyperLink.Create
description: THyperLink.Create
---

# THyperLink\.Create Method

## Overloads

* [THyperLink\.Create](#thyperlinkcreate)
* [THyperLink\.Create\(string, string, string, string\)](#thyperlinkcreatestring-string-string-string)
* [THyperLink\.Create\(THyperLinkType, string, string, string, string\)](#thyperlinkcreatethyperlinktype-string-string-string-string)
* [THyperLink\.Create\(THyperLinkType, string, string, string, string, string\)](#thyperlinkcreatethyperlinktype-string-string-string-string-string)
* [THyperLink\.Create\(THyperLinkType, string, string, string, string, string, string\)](#thyperlinkcreatethyperlinktype-string-string-string-string-string-string)

# THyperLink\.Create
Creates a new instance of a Hyperlink class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THyperLink/index.md">THyperLink</a>.Create: <a href="../THyperLink/index.md">THyperLink</a>; static; overload;</code></pre>

## See also

* [THyperLink](../THyperLink/index.md)

# THyperLink\.Create\(string, string, string, string\)
This overloads automatically infers the TextMark from a normal url\. LinkType is Url For example: http://myserver/myfile\.htm\#mytextmark will create a LinkType of Url and a TextMark of mytextmark\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THyperLink/index.md">THyperLink</a>.Create(const aUrl: string; const aDescription: string; const aTargetFrame: string; const aHint: string): <a href="../THyperLink/index.md">THyperLink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aUrl**|string|Url of the HyperLink\.|
|const|**aDescription**|string|Description of the HyperLink\.|
|const|**aTargetFrame**|string|Specifies the target frame that is to be used when opening this hyperlink\. When the hyperlink is activated this attribute is used to determine if a new window is launched for viewing or if an existing one can be used\.|
|const|**aHint**|string|Tooltip to be shown when hovering over the link\.|


## See also

* [THyperLink](../THyperLink/index.md)

# THyperLink\.Create\(THyperLinkType, string, string, string, string\)
Creates a new instance of a Hyperlink class\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THyperLink/index.md">THyperLink</a>.Create(const aLinkType: <a href="../THyperLinkType.md">THyperLinkType</a>; const aText: string; const aDescription: string; const aTargetFrame: string; const aTextMark: string): <a href="../THyperLink/index.md">THyperLink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLinkType**|[THyperLinkType](../THyperLinkType.md)|The type of hyperlink: to a local file, to a url, to a cell or to a networked file\.|
|const|**aText**|string|Text of the HyperLink\. This is empty when linking to a cell\.|
|const|**aDescription**|string|Description of the HyperLink\.|
|const|**aTargetFrame**|string|Specifies the target frame that is to be used when opening this hyperlink\. When the hyperlink is activated this attribute is used to determine if a new window is launched for viewing or if an existing one can be used\.|
|const|**aTextMark**|string|When entering a URL on Excel, you can enter additional text following the url with a "\#" character \(for example www\.your\_url\.com\#myurl"\) The text Mark is the text after the "\#" char\. When entering an address to a cell, the address goes here too\.|


## See also

* [THyperLink](../THyperLink/index.md)

# THyperLink\.Create\(THyperLinkType, string, string, string, string, string\)
Creates a new instance of a Hyperlink class, including a hint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THyperLink/index.md">THyperLink</a>.Create(const aLinkType: <a href="../THyperLinkType.md">THyperLinkType</a>; const aText: string; const aDescription: string; const aTargetFrame: string; const aTextMark: string; const aHint: string): <a href="../THyperLink/index.md">THyperLink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLinkType**|[THyperLinkType](../THyperLinkType.md)|The type of hyperlink: to a local file, to a url, to a cell or to a networked file\.|
|const|**aText**|string|Text of the HyperLink\. This is empty when linking to a cell\.|
|const|**aDescription**|string|Description of the HyperLink\.|
|const|**aTargetFrame**|string|Specifies the target frame that is to be used when opening this hyperlink\. When the hyperlink is activated this attribute is used to determine if a new window is launched for viewing or if an existing one can be used\.|
|const|**aTextMark**|string|When entering a URL on Excel, you can enter additional text following the url with a "\#" character \(for example www\.your\_url\.com\#myurl"\) The text Mark is the text after the "\#" char\. When entering an address to a cell, the address goes here too\.|
|const|**aHint**|string|Tooltip to be shown when hovering over the link\.|


## See also

* [THyperLink](../THyperLink/index.md)

# THyperLink\.Create\(THyperLinkType, string, string, string, string, string, string\)
Creates a new instance of a Hyperlink class, including a hint and a base Url\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THyperLink/index.md">THyperLink</a>.Create(const aLinkType: <a href="../THyperLinkType.md">THyperLinkType</a>; const aText: string; const aBaseUrl: string; const aDescription: string; const aTargetFrame: string; const aTextMark: string; const aHint: string): <a href="../THyperLink/index.md">THyperLink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLinkType**|[THyperLinkType](../THyperLinkType.md)|The type of hyperlink: to a local file, to a url, to a cell or to a networked file\.|
|const|**aText**|string|Text of the HyperLink\. This is empty when linking to a cell\.|
|const|**aBaseUrl**|string|Base Url used in all entries in the file\. This will combine with aText to give the full Url\.|
|const|**aDescription**|string|Description of the HyperLink\.|
|const|**aTargetFrame**|string|Specifies the target frame that is to be used when opening this hyperlink\. When the hyperlink is activated this attribute is used to determine if a new window is launched for viewing or if an existing one can be used\.|
|const|**aTextMark**|string|When entering a URL on Excel, you can enter additional text following the url with a "\#" character \(for example www\.your\_url\.com\#myurl"\) The text Mark is the text after the "\#" char\. When entering an address to a cell, the address goes here too\.|
|const|**aHint**|string|Tooltip to be shown when hovering over the link\.|


## See also

* [THyperLink](../THyperLink/index.md)


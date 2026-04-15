---
uid: ICssInformation
description: ICssInformation
---

# ICssInformation Interface

Encapsulates the information needed to create external CSS files\.
Note that if you use the same TCssInformation instance to create different html files, the CSS file created will be only one\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">ICssInformation = interface(IInterface);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Data](Data.md)|TTextWriter where an external CSS file will be stored\. If null, no CSS file will be created\. A link to a CSS file might be still included if you set the Url to a non null value\.<br />|
|[Url](Url.md)|URL of the css file that will be linked to this file\. If null, no CSS file will be created and all CSS information will be stored inside the html file\.<br />|
|[UrlNeedsEscaping](UrlNeedsEscaping.md)|If true \(the default\) the link you provide in [Url](Url.md) is not escaped and will be escaped by FlexCel\.<br />So for example, the link "http://my site" will be escaped to "http:&#8203;//&#8203;my%&#8203;%20site"&#8203;\.&#8203;<br />If the link you provided was already escaped, then set this variable to false\.<br />|



---
uid: THtmlEntities.EncodeAsHtml
description: THtmlEntities.EncodeAsHtml
---

# THtmlEntities\.EncodeAsHtml Method

## Overloads

* [THtmlEntities\.EncodeAsHtml\(string, THtmlVersion, TEncoding\)](#thtmlentitiesencodeashtmlstring-thtmlversion-tencoding)
* [THtmlEntities\.EncodeAsHtml\(string, THtmlVersion, TEncoding, TEnterStyle\)](#thtmlentitiesencodeashtmlstring-thtmlversion-tencoding-tenterstyle)

# THtmlEntities\.EncodeAsHtml\(string, THtmlVersion, TEncoding\)
Converts a normal string into a string that can be used inside an HTML file\. This includes converting characters to entities, replacing carriage returns by
tags, replacing multiple spaces by nbsp and more\. EnterStyle is TEnterStyle\.Br if omitted\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlEntities/index.md">THtmlEntities</a>.EncodeAsHtml(const originalString: string; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const encoding: TEncoding): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**originalString**|string|String we want to convert\.|
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)|Version of html we are targeting\. In Html 4<br />is valid and<br />is not\. In XHtml the inverse is true\.|
|const|**encoding**|TEncoding|Code page used to encode the string\. Normally this is UTF\-8|


## See also

* [THtmlEntities](../THtmlEntities/index.md)

# THtmlEntities\.EncodeAsHtml\(string, THtmlVersion, TEncoding, TEnterStyle\)
Converts a normal string into a string that can be used inside an HTML file\. This includes converting characters to entities, replacing carriage returns by
tags, replacing multiple spaces by nbsp and more\. EnterStyle is TEnterStyle\.Br if omitted\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlEntities/index.md">THtmlEntities</a>.EncodeAsHtml(const originalString: string; const htmlVersion: <a href="../THtmlVersion.md">THtmlVersion</a>; const encoding: TEncoding; const EnterStyle: <a href="../TEnterStyle.md">TEnterStyle</a>): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**originalString**|string|String we want to convert\.|
|const|**htmlVersion**|[THtmlVersion](../THtmlVersion.md)|Version of html we are targeting\. In Html 4<br />is valid and<br />is not\. In XHtml the inverse is true\.|
|const|**encoding**|TEncoding|Code page used to encode the string\. Normally this is UTF\-8|
|const|**EnterStyle**|[TEnterStyle](../TEnterStyle.md)|How to convert enters and multiple spaces in the text\.|


## See also

* [THtmlEntities](../THtmlEntities/index.md)


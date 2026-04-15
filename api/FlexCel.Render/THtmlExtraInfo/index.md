---
uid: THtmlExtraInfo
description: THtmlExtraInfo
---

# THtmlExtraInfo Class

Stores extra data to write in the HTML file\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">THtmlExtraInfo = class(TFlexCelObject);</code></pre>

## Properties

|Name|Description|
|---|---|
|[Title](Title.md)|Title of the HTML file\. If left null, the title of the page will be used\.<br />|
|[Meta](Meta.md)|Extra strings to be added in the meta section of the header\. You could specify keywords here, for example\.<br />|
|[HeadStart](HeadStart.md)|Extra strings to be added after the opening \<head> tag\.<br />|
|[HeadEnd](HeadEnd.md)|Extra strings to be added before the closing \</head> tag\.<br />|
|[BodyStart](BodyStart.md)|Extra strings to be added after the opening \<body> tag and before the table data\.<br />|
|[BodyEnd](BodyEnd.md)|Extra strings to be added before the closing \</body> tag and after the table data\.<br />|
|[PrintAreaSeparator](PrintAreaSeparator.md)|Extra strings to be added after each section of a non\-contiguous print area has been exported\.<br />Note that normally print areas are square, and in that case this property has no effect\. This property only works when the print area has more than one section\.<br />|



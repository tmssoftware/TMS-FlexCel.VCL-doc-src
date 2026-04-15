---
uid: TDrawingHyperlink.Create
description: TDrawingHyperlink.Create
---

# TDrawingHyperlink\.Create Method

## Overloads

* [TDrawingHyperlink\.Create](#tdrawinghyperlinkcreate)
* [TDrawingHyperlink\.Create\(string, string, string, string, Boolean, Boolean, Boolean\)](#tdrawinghyperlinkcreatestring-string-string-string-boolean-boolean-boolean)
* [TDrawingHyperlink\.Create\(string, string, string, string, string, Boolean, Boolean, Boolean\)](#tdrawinghyperlinkcreatestring-string-string-string-string-boolean-boolean-boolean)

# TDrawingHyperlink\.Create
Creates a new hyperlink for a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>.Create: <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; static; overload;</code></pre>

## See also

* [TDrawingHyperlink](../TDrawingHyperlink/index.md)

# TDrawingHyperlink\.Create\(string, string, string, string, Boolean, Boolean, Boolean\)
Creates a new hyperlink for a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>.Create(const aUrl: string; const aTargetFrame: string; const aHint: string; const aAction: string; const aHighlightClick: Boolean; const aAddToHistory: Boolean; const aEndsSounds: Boolean): <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aUrl**|string|Url for the link \(including the prefix like "file:///"\)|
|const|**aTargetFrame**|string|If blank then a new window will be used\.|
|const|**aHint**|string|Tooltip to show when the user hovers over the hyperlink\.|
|const|**aAction**|string|Specifies an action that is to be taken when this hyperlink is activated\. This can be used to specify a slide to be navigated to or a script of code to be run\. Doesn't seem to be used in Excel\.|
|const|**aHighlightClick**|Boolean|When set to true, the link will be painted in a "Visited" color\.|
|const|**aAddToHistory**|Boolean|If true, the link will be added to the history\.|
|const|**aEndsSounds**|Boolean|If true, any sound currently playing will be stopped when you click the link\.|


## See also

* [TDrawingHyperlink](../TDrawingHyperlink/index.md)

# TDrawingHyperlink\.Create\(string, string, string, string, string, Boolean, Boolean, Boolean\)
Creates a new hyperlink for a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>.Create(const aUrl: string; const aBaseUrl: string; const aTargetFrame: string; const aHint: string; const aAction: string; const aHighlightClick: Boolean; const aAddToHistory: Boolean; const aEndsSounds: Boolean): <a href="../TDrawingHyperlink/index.md">TDrawingHyperlink</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aUrl**|string|Url for the link \(including the prefix like "file:///"\)|
|const|**aBaseUrl**|string|Base Url for the link which will be combined with aUrl\.|
|const|**aTargetFrame**|string|If blank then a new window will be used\.|
|const|**aHint**|string|Tooltip to show when the user hovers over the hyperlink\.|
|const|**aAction**|string|Specifies an action that is to be taken when this hyperlink is activated\. This can be used to specify a slide to be navigated to or a script of code to be run\. Doesn't seem to be used in Excel\.|
|const|**aHighlightClick**|Boolean|When set to true, the link will be painted in a "Visited" color\.|
|const|**aAddToHistory**|Boolean|If true, the link will be added to the history\.|
|const|**aEndsSounds**|Boolean|If true, any sound currently playing will be stopped when you click the link\.|


## See also

* [TDrawingHyperlink](../TDrawingHyperlink/index.md)


---
uid: TUIFont.GetWidth
description: TUIFont.GetWidth
---

# TUIFont\.GetWidth Method

Returns the width of a string in device\-independent pixels at dpi resolution when written in the current font\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUIFont/index.md">TUIFont</a>.GetWidth(const aText: string; const dpi: Integer; const aReadingOrder: <a href="../TFlxReadingOrder.md">TFlxReadingOrder</a>): Double; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aText**|string|Text we want to measure\.|
|const|**dpi**|Integer|Dpi to measure the string\.|
|const|**aReadingOrder**|[TFlxReadingOrder](../TFlxReadingOrder.md)|Reading order for the document where the string is\.|


## See also

* [TUIFont](../TUIFont/index.md)


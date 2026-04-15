---
uid: TUIFont.CreateSimilarFont
description: TUIFont.CreateSimilarFont
---

# TUIFont\.CreateSimilarFont Method

Creates a font which is the most similar to the one you specify\. Some fonts don't have specific styles like italics or bold, if this is the case, this method will return the same font with a different style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUIFont/index.md">TUIFont</a>.CreateSimilarFont(const FontName: string; const FontSize: Double; const FontStyle: <a href="../TUIFontStyle.md">Set of TUIFontStyle</a>): <a href="../TUIFont/index.md">TUIFont</a>; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**FontName**|string|Name of the font we wish to create\.|
|const|**FontSize**|Double|Size in points of the font\.|
|const|**FontStyle**|[Set of TUIFontStyle](../TUIFontStyle.md)|Style of the font\.|


## Returns

The font if it was possible to create it, or a similar one if it wasn't\.

## See also

* [TUIFont](../TUIFont/index.md)


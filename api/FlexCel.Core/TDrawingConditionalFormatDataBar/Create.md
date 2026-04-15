---
uid: TDrawingConditionalFormatDataBar.Create
description: TDrawingConditionalFormatDataBar.Create
---

# TDrawingConditionalFormatDataBar\.Create Method

Creates a new struct and initialized the data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingConditionalFormatDataBar/index.md">TDrawingConditionalFormatDataBar</a>.Create(const aHasDataBar: Boolean; const aHideValues: Boolean; const aRectangle: <a href="../TUIRectangle/index.md">TUIRectangle</a>; const aFillColor: <a href="../TUIColor/index.md">TUIColor</a>; const aBorderColor: <a href="../TUIColor/index.md">TUIColor</a>; const aAxisColor: <a href="../TUIColor/index.md">TUIColor</a>; const aIsGradient: Boolean; const aIsRightToLeft: Boolean): <a href="../TDrawingConditionalFormatDataBar/index.md">TDrawingConditionalFormatDataBar</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aHasDataBar**|Boolean|If true, the format has a databar\.|
|const|**aHideValues**|Boolean|If true, the cell text won't be displayed\.|
|const|**aRectangle**|[TUIRectangle](../TUIRectangle/index.md)|Rectangle of the databar in coordinates relative to the cell\. 0 means Left and Top, 1 right and bottom\.|
|const|**aFillColor**|[TUIColor](../TUIColor/index.md)|Color for the fill of the databar\.|
|const|**aBorderColor**|[TUIColor](../TUIColor/index.md)|Color for the border of the DataBar\. TUIColor\.Empty means no border\.|
|const|**aAxisColor**|[TUIColor](../TUIColor/index.md)|Color for the axis where the databar crosses 0\. If this is TUIColor\.Empty, no axis should be drawn\.<br />If not empty the position depends in the value of [IsRightToLeft](IsRightToLeft.md) parameter\.|
|const|**aIsGradient**|Boolean|If true, this databar has a gradient fill\.|
|const|**aIsRightToLeft**|Boolean|If true, the databar goes right to left and the gradient must go right to left too\.|


## See also

* [TDrawingConditionalFormatDataBar](../TDrawingConditionalFormatDataBar/index.md)


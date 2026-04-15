---
uid: TDrawingColor.FromColor
description: TDrawingColor.FromColor
---

# TDrawingColor\.FromColor Method

Returns a color class with a specified color\. There is no real need to call this method, since conversion between  [TDrawingColor](../TDrawingColor/index.md) and [TUIColor](../TUIColor/index.md) is implicit\. You can just assign Color to this class and viceversa\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingColor/index.md">TDrawingColor</a>.FromColor(const aColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TDrawingColor/index.md">TDrawingColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|[TUIColor](../TUIColor/index.md)|Color that we want to set\.|


## Returns

The corresponding system color\.

## See also

* [TDrawingColor](../TDrawingColor/index.md)


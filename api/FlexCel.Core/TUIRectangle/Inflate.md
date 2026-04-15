---
uid: TUIRectangle.Inflate
description: TUIRectangle.Inflate
---

# TUIRectangle\.Inflate Method

## Overloads

* [TUIRectangle\.Inflate\(Double, Double\)](#tuirectangleinflatedouble-double)
* [TUIRectangle\.Inflate\(TUIRectangle, Double, Double\)](#tuirectangleinflatetuirectangle-double-double)

# TUIRectangle\.Inflate\(Double, Double\)
Subtracts dx from the left and adds dx to the right\. Subtracts dy from the top and adds dy to the bottom\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TUIRectangle/index.md">TUIRectangle</a>.Inflate(const dx: Double; const dy: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**dx**|Double|Value to inflate the rectangle in the x direction\.|
|const|**dy**|Double|Value to inflate the rectangle in the y direction\.|


## See also

* [TUIRectangle](../TUIRectangle/index.md)

# TUIRectangle\.Inflate\(TUIRectangle, Double, Double\)
Inflates the rectangle by \(dx, dy\)\. It is similar to the other inflate overload, but this is a static method, it won't modify a rectangle in place\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TUIRectangle/index.md">TUIRectangle</a>.Inflate(const sourceRect: <a href="../TUIRectangle/index.md">TUIRectangle</a>; const dx: Double; const dy: Double): <a href="../TUIRectangle/index.md">TUIRectangle</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceRect**|[TUIRectangle](../TUIRectangle/index.md)|Rectangle with the original coordinates\.|
|const|**dx**|Double|X offset to inflate\.|
|const|**dy**|Double|Y offset to inflate\.|


## See also

* [TUIRectangle](../TUIRectangle/index.md)


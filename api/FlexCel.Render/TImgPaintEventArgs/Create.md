---
uid: TImgPaintEventArgs.Create
description: TImgPaintEventArgs.Create
---

# TImgPaintEventArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TImgPaintEventArgs/index.md">TImgPaintEventArgs</a>.Create(const aGraphics: <a href="../../FlexCel.Core/TUIGraphics/index.md">TUIGraphics</a>; const aPageBounds: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; const aCurrentPage: Integer; const aCurrentPageInSheet: Integer; const aTotalPages: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aGraphics**|[TUIGraphics](../../FlexCel.Core/TUIGraphics/index.md)|Gets the graphics used to paint\.|
|const|**aPageBounds**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|Gets the rectangle in which to paint\.|
|const|**aCurrentPage**|Integer|The page we are printing\.|
|const|**aCurrentPageInSheet**|Integer|The page we are printing, relative to the current sheet\.|
|const|**aTotalPages**|Integer|The total number of pages we have available to export\.|


## See also

* [TImgPaintEventArgs](../TImgPaintEventArgs/index.md)


---
uid: TBookmark.Create
description: TBookmark.Create
---

# TBookmark\.Create Constructor

## Overloads

* [TBookmark\.Create\(string, TPdfDestination, Boolean\)](#tbookmarkcreatestring-tpdfdestination-boolean)
* [TBookmark\.Create\(string, TPdfDestination, Boolean, TUIColor, TBookmarkStyleSet\)](#tbookmarkcreatestring-tpdfdestination-boolean-tuicolor-tbookmarkstyleset)

# TBookmark\.Create\(string, TPdfDestination, Boolean\)
Creates a new TBookmark instance\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBookmark/index.md">TBookmark</a>.Create(const aTitle: string; const aDestination: <a href="../TPdfDestination/index.md">TPdfDestination</a>; const aChildrenCollapsed: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTitle**|string|Title of the bookmark item\.|
|const|**aDestination**|[TPdfDestination](../TPdfDestination/index.md)|Page where the bookmark points to\.|
|const|**aChildrenCollapsed**|Boolean|If true all children from this bookmark will be collapsed\.|


## See also

* [TBookmark](../TBookmark/index.md)

# TBookmark\.Create\(string, TPdfDestination, Boolean, TUIColor, TBookmarkStyleSet\)
Creates a new TBookmark instance\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBookmark/index.md">TBookmark</a>.Create(const aTitle: string; const aDestination: <a href="../TPdfDestination/index.md">TPdfDestination</a>; const aChildrenCollapsed: Boolean; const aTextColor: <a href="../../FlexCel.Core/TUIColor/index.md">TUIColor</a>; const aTextStyle: <a href="../TBookmarkStyle.md">Set of TBookmarkStyle</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTitle**|string|Title of the bookmark item\.|
|const|**aDestination**|[TPdfDestination](../TPdfDestination/index.md)|Page where the bookmark points to\.|
|const|**aChildrenCollapsed**|Boolean|If true all children from this bookmark will be collapsed\.|
|const|**aTextColor**|[TUIColor](../../FlexCel.Core/TUIColor/index.md)|Text color for the bookmark entry\.|
|const|**aTextStyle**|[Set of TBookmarkStyle](../TBookmarkStyle.md)|Text style for the bookmark entry\.|


## See also

* [TBookmark](../TBookmark/index.md)


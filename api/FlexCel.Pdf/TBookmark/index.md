---
uid: TBookmark
description: TBookmark
---

# TBookmark Class

An entry on the Bookmark list for a PDF file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TBookmark = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string, TPdfDestination, Boolean\)](Create.md#tbookmarkcreatestring-tpdfdestination-boolean)<br />  [Create\(string, TPdfDestination, Boolean, TUIColor, TBookmarkStyleSet\)](Create.md#tbookmarkcreatestring-tpdfdestination-boolean-tuicolor-tbookmarkstyleset)<br />|


## Methods

|Name|Description|
|---|---|
|[AddChild](AddChild.md)|Adds a new child of this bookmark on the outline\.<br />|
|[Child](Child.md)|Returns one child of the current bookmark\.<br />|
|[AllOpenCount](AllOpenCount.md)|Returns a list of all open children of this bookmark\. Mostly for internal use\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Title](Title.md)|Title of the bookmark item\.<br />|
|[Destination](Destination.md)|Page where the bookmark points to\.<br />|
|[ChildrenCollapsed](ChildrenCollapsed.md)|If true, all children of this bookmark will be collapsed\.<br />|
|[TextColor](TextColor.md)|Text color for the bookmark entry\.<br />|
|[TextStyle](TextStyle.md)|Text style for the bookmark entry\.<br />|
|[ChildCount](ChildCount.md)|Returns the number of children of this bookmark\.<br />|



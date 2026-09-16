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
|[AllOpenCount](AllOpenCount.md)|Returns a list of all open children of this bookmark\. Mostly for internal use\.<br />|
|[Child](Child.md)|Returns one child of the current bookmark\.<br />|
|[Clone](Clone.md)|Returns a deep copy of this object\.<br />|


## Properties

|Name|Description|
|---|---|
|[ChildCount](ChildCount.md)|Returns the number of children of this bookmark\.<br />|
|[ChildrenCollapsed](ChildrenCollapsed.md)|If true, all children of this bookmark will be collapsed\.<br />|
|[Destination](Destination.md)|Page where the bookmark points to\.<br />|
|[TextColor](TextColor.md)|Text color for the bookmark entry\.<br />|
|[TextStyle](TextStyle.md)|Text style for the bookmark entry\.<br />|
|[Title](Title.md)|Title of the bookmark item\.<br />|



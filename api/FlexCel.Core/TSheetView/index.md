---
uid: TSheetView
description: TSheetView
---

# TSheetView Record

This class has the different "Page View" modes that you can choose in Excel, ad properties of each mode\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TSheetView = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TSheetView with the specified values\.<br />|
|[Equals](Equals.md)|Returns true if both object are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the instance\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ViewType](ViewType.md)|Active view mode\.<br />|
|[ShowWhitespace](ShowWhitespace.md)|If true, when in Page Layout mode Excel will show whitespace between sheets\.<br />|
|[ShowRulers](ShowRulers.md)|If true, Excel will show rulers when in Page Layout mode\.<br />|
|[ZoomNormal](ZoomNormal.md)|Zoom for when we are in normal mode\. It must be 0, or a value between 10 and 400\. Zero means to use the default zoom\.<br />|
|[ZoomPageLayout](ZoomPageLayout.md)|Zoom for when we are in Page Layout mode\. It must be 0, or a value between 10 and 400\. Zero means to use the default zoom\.<br />|
|[ZoomPageBreakPreview](ZoomPageBreakPreview.md)|Zoom for when we are in Page Break Preview mode\. It must be 0, or a value between 10 and 400\. Zero means to use the default zoom which is 60%% for Excel 2013\.<br />|



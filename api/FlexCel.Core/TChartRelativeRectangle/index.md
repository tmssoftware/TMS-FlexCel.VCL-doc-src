---
uid: TChartRelativeRectangle
description: TChartRelativeRectangle
---

# TChartRelativeRectangle Record

A rectangle used in charts that is relative to a parent rectangle\. The coordinates of the rectangle go between 0 and 1 where 0 means 0%% of the coordinate of the parent, and 1 means 100%%\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TChartRelativeRectangle = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TChartRelative&#8203;Rectangle\.&#8203;<br />|
|[CalcRect](CalcRect.md)|**Overloaded<br />**  [CalcRect\(TUIPointF, TUIRectangle\)](CalcRect.md#tchartrelativerectanglecalcrecttuipointf-tuirectangle)<br />  [CalcRect\(TUIPointF, TUIRectangle, Double, Double\)](CalcRect.md#tchartrelativerectanglecalcrecttuipointf-tuirectangle-double-double)<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[X1](X1.md)|Percent of the parent coordinate\. 0 means parent\.Left and 1 means parent\.Right\.<br />|
|[Y1](Y1.md)|Percent of the parent coordinate\. 0 means parent\.Top and 1 means parent\.Bottom\.<br />|
|[X2](X2.md)|Percent of the parent coordinate\. This value depends on [WidthMode](WidthMode.md)\.<br />If WidthMode is Factor, then 0 means 0 width, and 1 the width of the parent\.<br />If WidthMode is Edge, then 0 means parent\.Left and 1 means parent\.Right\.<br />|
|[Y2](Y2.md)|Percent of the parent coordinate\. This value depends on [HeightMode](HeightMode.md)\.<br />If HeightMode is Factor, then 0 means 0 height, and 1 the height of the parent\.<br />If HeightMode is Edge, then 0 means parent\.Top and 1 means parent\.Bottom\.<br />|
|[XMode](XMode.md)|Defines how [X1](X1.md) behaves\. When this value is Factor, X1 is a percent of the offset from the default position\.<br />When this value is Edge, X1 is the left coordinate of the point\.<br />|
|[YMode](YMode.md)|Defines how [Y1](Y1.md) behaves\. When this value is Factor, Y1 is a percent of offset from the default position\.<br />When this value is Edge, Y1 is the top coordinate of the point\.<br />|
|[WidthMode](WidthMode.md)|Defines how [X2](X2.md) behaves\. When this value is Factor, X2 is a percent of the width of the rectangle\.<br />When this value is Edge, X2 is the right coordinate of the rectangle\.<br />|
|[HeightMode](HeightMode.md)|Defines how [Y2](Y2.md) behaves\. When this value is Factor, Y2 is a percent of the height of the rectangle\.<br />When this value is Edge, Y2 is the bottom coordinate of the rectangle\.<br />|
|[Automatic](Automatic.md)|Returns a new rectangle with no position set\.<br />|



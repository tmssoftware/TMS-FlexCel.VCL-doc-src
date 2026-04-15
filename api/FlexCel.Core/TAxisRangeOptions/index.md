---
uid: TAxisRangeOptions
description: TAxisRangeOptions
---

# TAxisRangeOptions Class

Properties for the ranges of an axis\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TAxisRangeOptions = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Integer, Integer, Boolean, Boolean, Boolean\)](Create.md#taxisrangeoptionscreateinteger-integer-boolean-boolean-boolean)<br />  [Create\(Integer, Integer, Boolean, Boolean, Boolean, Boolean\)](Create.md#taxisrangeoptionscreateinteger-integer-boolean-boolean-boolean-boolean)<br />|


## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[LabelFrequency](LabelFrequency.md)|Frequency at what the labels on categories are displayed\. 0 Means automatic\. 1 means display all labels, 2 display one label and skip one, and so on\.<br />|
|[TickFrequency](TickFrequency.md)|Frequency at what the ticks on categories are displayed\. 1 means display all ticks, 2 display one tick and skip one, and so on\.<br />|
|[ValueAxisBetween&#8203;Categories](ValueAxisBetweenCategories.md)|Specifies if the Y Axis crosses between categories or in the middle of one\. Normally a Column Chart  cross in the middle, and an area chart will cross between\.<br />|
|[ValueAxisAtMaxCategory](ValueAxisAtMaxCategory.md)|True if the Y axis is at the left\.<br />|
|[ReverseCategories](ReverseCategories.md)|True if categories should be printed in reverse order\.<br />|
|[MultiLevelLabels](MultiLevelLabels.md)|If false, then category labels won't be rendered as multilevel, even if they have multiple levels of data\.<br />|



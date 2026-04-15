---
uid: TFillStyleList
description: TFillStyleList
---

# TFillStyleList Class

Represents the fill style characteristics for an autoshape\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFillStyleList = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TFillStyleList instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Creates a deep copy of this object\.<br />|
|[Add](Add.md)|Adds a new FillStyle to the collection\. Fill styles must be added in order, first is "Subtle", second is "Moderate", third is "Intense" and there could be new definitions in newer versions of Excel\.<br />|
|[GetRealFillStyle](GetRealFillStyle.md)|Returns the fill style that results from applying the formatting type to a color\.<br />|
|[Clear](Clear.md)|Clears all the formatting definitions\.<br />|


## Properties

|Name|Description|
|---|---|
|[Count](Count.md)|Returns the number of elements stored in this collection\.<br />|
|[Item\[const index\]](Itemconst-index.md)|Returns the fill style for a given formatting type\. Currently Excel defines only 3 formatting types, but more could be added in the future\.<br />If you need to access a formatting type that is not defined in the [TFormattingType](../TFormattingType.md) enumeration, just cast an integer to TFormattingType\.<br />|



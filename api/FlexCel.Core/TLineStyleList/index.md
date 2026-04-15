---
uid: TLineStyleList
description: TLineStyleList
---

# TLineStyleList Class

Represents the line style characteristics\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TLineStyleList = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|
|[GetRealFillStyle](GetRealFillStyle.md)|Returns the line color that results from applying the formatting type to a color\.<br />|
|[Add](Add.md)|Adds a new LineStyle to the collection\. Line styles must be added in order, first is "Subtle", second is "Moderate", third is "Intense" and there could be new definitions in newer versions of Excel\.<br />|


## Properties

|Name|Description|
|---|---|
|[Count](Count.md)|Count of line styles\.<br />|
|[Item\[const index\]](Itemconst-index.md)|Returns the line style for a given formatting type\. Currently Excel defines only 3 formatting types, but more could be added in the future\.<br />If you need to access a formatting type that is not defined in the [TFormattingType](../TFormattingType.md) enumeration, just cast an integer to TFormattingType\.<br />|



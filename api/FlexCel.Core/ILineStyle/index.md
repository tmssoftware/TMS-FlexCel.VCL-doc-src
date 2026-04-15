---
uid: ILineStyle
description: ILineStyle
---

# ILineStyle Interface

Definition for a Drawing line style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ILineStyle = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Clone](Clone.md)|Returns a deep copy of the fill style\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1, 0 or 1 depending if the object is smaller, equal or bigger than the other\.<br />|


## Properties

|Name|Description|
|---|---|
|[Fill](Fill.md)|Line color and/or fill\.<br />|
|[Width](Width.md)|Width of the line in EMUs \(1 pt = 12700 EMUs\)\. If null, width of the theme will be used\.<br />|
|[PenAlign](PenAlign.md)|Specifies the alignment to be used for the underline stroke\. If null, default from the theme will be used\.<br />|
|[LineCap](LineCap.md)|How the line ends\. If null, default from the theme will be used\.<br />|
|[CompoundLineType](CompoundLineType.md)|Compound line style\. If null, default from the theme will be used\.<br />|
|[Dashing](Dashing.md)|Line dashing\. If null, default from the theme will be used\.<br />|
|[Join](Join.md)|How the line joins with the next\. If null, default from the theme will be used\.<br />|
|[MiterLim](MiterLim.md)|The amount by which lines is extended to form a miter join, when [Join](Join.md) is [TLineJoin.Miter](../TLineJoin.md)\.<br />|
|[HeadArrow](HeadArrow.md)|Head arrow if it has one\. If null, default from the theme will be used\.<br />|
|[TailArrow](TailArrow.md)|Tail arrow if it has one\. If null, default from the theme will be used\.<br />|



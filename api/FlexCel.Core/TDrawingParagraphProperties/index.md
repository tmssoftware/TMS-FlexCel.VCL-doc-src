---
uid: TDrawingParagraphProperties
description: TDrawingParagraphProperties
---

# TDrawingParagraphProperties Record

Properties of a text paragraph inside a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingParagraphProperties = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance by setting all properties\.<br />|
|[FromAlign](FromAlign.md)|Returns an empty paragraph with a specific align\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both strings are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same string and formatting\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|


## Properties

|Name|Description|
|---|---|
|[Empty](Empty.md)|Returns a paragraph with the default values\.<br />|
|[MarL](MarL.md)|Specifies the left margin of the paragraph\.<br />|
|[MarR](MarR.md)|Specifies the right margin of the paragraph\.<br />|
|[Lvl](Lvl.md)|Specifies the particular level text properties that this paragraph follows\.<br />|
|[Indent](Indent.md)|Specifies the indent size that is applied to the first line of text in the paragraph\. An  indentation of 0 is considered to be at the same location as marL attribute\.<br />|
|[Algn](Algn.md)|Specifies the alignment that is to be applied to the paragraph\.<br />|
|[DefTabSz](DefTabSz.md)|Specifies the default size for a tab character within this paragraph\. This attribute should  be used to describe the spacing of tabs within the paragraph instead of a leading  indentation tab\. For indentation tabs there are the marL and indent attributes to assist with this\.<br />|
|[Rtl](Rtl.md)|Specifies whether the text is right\-to\-left or left\-to\-right in its flow direction\. If null, the value is not known\.<br />|
|[EaLnBrk](EaLnBrk.md)|Specifies whether an East Asian word can be broken in half and wrapped onto the next line without a hyphen being added\.<br />|
|[FontAlgn](FontAlgn.md)|Determines where vertically on a line of text the actual words are positioned\. This deals  with vertical placement of the characters with respect to the baselines\.<br />|
|[LatinLnBrk](LatinLnBrk.md)|Specifies whether a Latin word can be broken in half and wrapped onto the next line without a hyphen being added\.<br />|
|[HangingPunct](HangingPunct.md)|Specifies whether punctuation is to be forcefully laid out on a line of text or put on a different line of text\.<br />|
|[DefaultTextRun&#8203;Properties](DefaultTextRunProperties.md)|Default text properties for the text inside a paragraph\.<br />|
|[HasDefaultText&#8203;RunProperties](HasDefaultTextRunProperties.md)|Returns true if the paragraph has defined [DefaultTextRun&#8203;Properties](DefaultTextRunProperties.md) even if it is empty\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if no members are set\.<br />|



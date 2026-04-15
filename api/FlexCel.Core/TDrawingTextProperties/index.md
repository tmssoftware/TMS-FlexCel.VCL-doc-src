---
uid: TDrawingTextProperties
description: TDrawingTextProperties
---

# TDrawingTextProperties Record

Properties of a text run inside a drawing\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingTextProperties = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(IFillStyle, TDrawingTextAttributes\)](Create.md#tdrawingtextpropertiescreateifillstyle-tdrawingtextattributes)<br />  [Create\(IFillStyle, ILineStyle, IEffectProperties, NullableTDrawingColor, TDrawingUnderline, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, NullableTThemeTextFont, TDrawingHyperlink, TDrawingHyperlink, Boolean, TDrawingTextAttributes\)](Create.md#tdrawingtextpropertiescreateifillstyle-ilinestyle-ieffectproperties-nullabletdrawingcolor-tdrawingunderline-nullabletthemetextfont-nullabletthemetextfont-nullabletthemetextfont-nullabletthemetextfont-tdrawinghyperlink-tdrawinghyperlink-boolean-tdrawingtextattributes)<br />|
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
|[Empty](Empty.md)|Returns the text attributes with the default values\.<br />|
|[Fill](Fill.md)|Fill style for the text\.<br />|
|[Line](Line.md)|Line style for the text\.<br />|
|[Effects](Effects.md)|Effects applied to the text\.<br />|
|[Highlight](Highlight.md)|Highlight color that is present for a run of text\.<br />|
|[Underline](Underline.md)|Underline fill for the text\.<br />|
|[Latin](Latin.md)|This element specifies that a Latin font be used for a specific run of text\. This font is specified with a typeface  attribute much like the others but is specifically classified as a Latin font\.<br />|
|[EastAsian](EastAsian.md)|This element specifies that an East Asian font be used for a specific run of text\. This font is specified with a  typeface attribute much like the others but is specifically classified as an East Asian font\.<br />|
|[ComplexScript](ComplexScript.md)|This element specifies that a complex script font be used for a specific run of text\. This font is specified with a  typeface attribute much like the others but is specifically classified as a complex script font\.<br />|
|[Symbol](Symbol.md)|This element specifies that a symbol script font be used for a specific run of text\. This font is specified with a  typeface attribute much like the others but is specifically classified as a symbol script font\.<br />|
|[HyperlinkClick](HyperlinkClick.md)|Specifies the on\-click hyperlink information to be applied to a run of text\. When the hyperlink text is clicked the  link is fetched\.<br />|
|[HyperlinkMouseOver](HyperlinkMouseOver.md)|Specifies the mouse\-over hyperlink information to be applied to a run of text\. When the mouse is hovered over  this hyperlink text the link is fetched\.<br />|
|[RightToLeft](RightToLeft.md)|This element specifies whether the contents of this run shall have right\-to\-left characteristics\.<br />|
|[Attributes](Attributes.md)|Group of simple attributes applied to the text run\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if no members are set\.<br />|



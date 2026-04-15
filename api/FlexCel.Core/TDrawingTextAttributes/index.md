---
uid: TDrawingTextAttributes
description: TDrawingTextAttributes
---

# TDrawingTextAttributes Record

Group of simple attributes for text properties\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingTextAttributes = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string, NullableRealNumber\)](Create.md#tdrawingtextattributescreatestring-nullablerealnumber)<br />  [Create\(NullableBoolean, string, string, NullableInt32, NullableBoolean, NullableBoolean, NullableTDrawingUnderlineStyle, NullableTDrawingTextStrike, NullableInt32, NullableTDrawingTextCapitalization, NullableTDrawingCoordinate, NullableBoolean, NullableRealNumber, NullableBoolean, Boolean, Boolean, Boolean, Integer, string\)](Create.md#tdrawingtextattributescreatenullableboolean-string-string-nullableint32-nullableboolean-nullableboolean-nullabletdrawingunderlinestyle-nullabletdrawingtextstrike-nullableint32-nullabletdrawingtextcapitalization-nullabletdrawingcoordinate-nullableboolean-nullablerealnumber-nullableboolean-boolean-boolean-boolean-integer-string)<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both strings are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same string and formatting\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the attributes are empty|


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
|[Kumimoji](Kumimoji.md)|Specifies whether the numbers contained within vertical text continue vertically with the  text or whether they are to be displayed horizontally while the surrounding characters  continue in a vertical fashion\. A null value means to use the parent's settings\.<br />|
|[Lang](Lang.md)|Specifies the language to be used when the generating application is displaying the user  interface controls\.<br />|
|[AltLang](AltLang.md)|Specifies the alternate language to use when the generating application is displaying the  user interface controls\.<br />|
|[Size](Size.md)|Specifies the size of text within a text run\. Whole points are specified in increments of  100 starting with 100 being a point size of 1\. For instance a font point size of 12 would be  1200 and a font point size of 12\.5 would be 1250\. A null value means to use the parent's settings\.<br />|
|[Bold](Bold.md)|Specifies whether a run of text is formatted as bold text\. A null value means to use the parent's settings, while false means always that the text is not bold, no matter if it was inside a bold paragraph\.<br />|
|[Italic](Italic.md)|Specifies whether a run of text is formatted as italic text\. A null value means to use the parent's settings\.<br />|
|[Underline](Underline.md)|Specifies whether a run of text is formatted as underlined text\.  A null value means to use the parent's settings\.<br />|
|[Strike](Strike.md)|Specifies whether a run of text is formatted as strikethrough text\. A null value means to use the parent's settings\.<br />|
|[Kern](Kern.md)|Specifies the minimum font size at which character kerning occurs for this text run\.<br />Whole points are specified in increments of 100 starting with 100 being a point size of 1\.<br />For instance a font point size of 12 would be 1200 and a font point size of 12\.5 would be  1250\. A null value means to use the parent's settings\.<br />|
|[Capitalization](Capitalization.md)|Specifies the capitalization that is to be applied to the text run\. This is a render\-only  modification and does not affect the actual characters stored in the text run\. This  attribute is also distinct from the toggle function where the actual characters stored in  the text run are changed\. A null value means to use the parent's settings\.<br />|
|[Spacing](Spacing.md)|Specifies the spacing between characters within a text run\. This spacing is specified  numerically and should be consistently applied across the entire run of text by the  generating application\. Whole points are specified in increments of 100 starting with 100  being a point size of 1\. For instance a font point size of 12 would be 1200 and a font point  size of 12\.5 would be 1250\. A null value means to use the parent's settings\.<br />|
|[NormalizeH](NormalizeH.md)|Specifies the normalization of height that is to be applied to the text run\. This is a render\- only modification and does not affect the actual characters stored in the text run\. This  attribute is also distinct from the toggle function where the actual characters stored in  the text run are changed\. A null value means to use the parent's settings\.<br />|
|[Baseline](Baseline.md)|Specifies the baseline for both the superscript and subscript fonts\. A null value means to use the parent's settings\.<br />|
|[NoProof](NoProof.md)|Specifies that a run of text has been selected by the user to not be checked for mistakes\. A null value means to use the parent's settings\.<br />|
|[Dirty](Dirty.md)|Specifies that the content of a text run has changed since the proofing tools have last been run\.<br />|
|[Err](Err.md)|Specifies that when this run of text was checked for spelling, grammar, etc\. that a mistake was indeed found\.<br />|
|[SmartTagClean](SmartTagClean.md)|Specifies whether or not a text run has been checked for smart tags\.<br />|
|[SmartTagId](SmartTagId.md)|Specifies a smart tag identifier for a run of text\. This ID is unique throughout the  presentation and is used to reference corresponding auxiliary information about the  smart tag\.<br />|
|[BookmarkLinkTarget](BookmarkLinkTarget.md)|Specifies the link target name that is used to reference to the proper link properties in a  custom XML part within the document\.<br />|



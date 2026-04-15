---
uid: TDrawingTextParagraph
description: TDrawingTextParagraph
---

# TDrawingTextParagraph Record

A paragraph in the text inside a drawing\. This struct is immutable\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingTextParagraph = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties\)](Create.md#tdrawingtextparagraphcreatetdrawingtextrunarray-tdrawingparagraphproperties-tdrawingtextproperties)<br />  [Create\(string, TDrawingParagraphProperties, TDrawingTextProperties\)](Create.md#tdrawingtextparagraphcreatestring-tdrawingparagraphproperties-tdrawingtextproperties)<br />  [Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties, string\)](Create.md#tdrawingtextparagraphcreatetdrawingtextrunarray-tdrawingparagraphproperties-tdrawingtextproperties-string)<br />|
|[TextRun](TextRun.md)|Returns a single text run for the paragraph\.<br />|
|[Substring](Substring.md)|Retrieves a substring from this instance\. The substring starts at a specified character position and has a specified length\.<br />|
|[ReplaceRun](ReplaceRun.md)|Returns a new paragraph with the run at position run replaced ny another\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both strings are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same string and formatting\.<br />|
|[WithNewFieldIds](WithNewFieldIds.md)|Returns a new TDrawingText&#8203;Paragraph with new field ids if the DrawingTextParagraph has field ids\.<br />While FlexCel will do this automatically when you link a shape, you can use this method when creating a new linked shape that requires new field ids\.<br />|


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
|[Properties](Properties.md)|The properties that apply to this paragraph\.<br />|
|[EndParagraph&#8203;Properties](EndParagraphProperties.md)|Properties that apply to new paragraphs that are added after this one\.<br />|
|[TextRunCount](TextRunCount.md)|Returns the number of runs in the paragraph\.<br />|
|[Text](Text.md)|Returns the contents of the paragraph as plain text\.<br />|
|[UnknownXml](UnknownXml.md)|Contains unknown xml read from an xlsx file\. If this property is not empty, then the value here will be used and the rest of properties will be ignored when saving the file\.<br />|
|[Runs](Runs.md)|Returns all the text runs for this paragraph\.<br />This creates a copy of the array of runs, so if possible use [TextRun](TextRun.md) instead to avoid memory allocations\.<br />|



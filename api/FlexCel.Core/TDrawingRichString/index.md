---
uid: TDrawingRichString
description: TDrawingRichString
---

# TDrawingRichString Record

A rich string used in drawings\. It is similar to [TRichString](../TRichString/index.md) but it has more  properties like for example wordart properties\. Similar to a string, this class is immutable\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingRichString = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tdrawingrichstringcreate)<br />  [Create\(string\)](Create.md#tdrawingrichstringcreatestring)<br />  [Create\(TDrawingTextParagraphArray\)](Create.md#tdrawingrichstringcreatetdrawingtextparagrapharray)<br />  [Create\(string, TDrawingAlignment\)](Create.md#tdrawingrichstringcreatestring-tdrawingalignment)<br />|
|[Paragraph](Paragraph.md)|A paragraph of the text\.<br />|
|[Substring](Substring.md)|**Overloaded<br />**  [Substring\(Integer\)](Substring.md#tdrawingrichstringsubstringinteger)<br />  [Substring\(Integer, Integer\)](Substring.md#tdrawingrichstringsubstringinteger-integer)<br />|
|[Add](Add.md)|Adds two richstrings together\. If using C\#, you can just use the overloaded "\+" operator to contactenate rich strings\.<br />|
|[Trim](Trim.md)|Trims all the whitespace at the beginning and end of the string\.<br />|
|[RightTrim](RightTrim.md)|Trims all the whitespace at the end of the string\.<br />|
|[ToString](ToString.md)|Returns the string without Rich text info\.<br />|
|[HasFields](HasFields.md)|Returns true if the TDrawingRichString has any fields that must be replaced by values\.<br />|
|[ToRichString](ToRichString.md)|**Overloaded<br />**  [ToRichString\(TCoreExcelFile, IShapeFont\)](ToRichString.md#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont)<br />  [ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont\)](ToRichString.md#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont)<br />  [ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>\)](ToRichString.md#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont-tfuncstring-trichstring)<br />  [ToRichString\(TCoreExcelFile, IShapeFont, TFlxFont, TFunc\<string, TRichString>, Boolean\)](ToRichString.md#tdrawingrichstringtorichstringtcoreexcelfile-ishapefont-tflxfont-tfuncstring-trichstring-boolean)<br />|
|[FirstRun](FirstRun.md)|Returns the first run of the text\. Note that an empty TDrawingRichText can have a run anyway, while a TRichString can't\.<br />If there is no first run, the returned value will have a a negative FirstChar\.<br />|
|[FromRichString](FromRichString.md)|**Overloaded<br />**  [FromRichString\(TRichString, TCoreExcelFile, TDrawingAlignment\)](FromRichString.md#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingalignment)<br />  [FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment\)](FromRichString.md#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingrichstring-tdrawingalignment)<br />  [FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment, Boolean\)](FromRichString.md#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingrichstring-tdrawingalignment-boolean)<br />|
|[ReplaceText](ReplaceText.md)|Replaces the existing text in this struct with the text in rs, keeping the properties of the text\.<br />|
|[GetTextProperties](GetTextProperties.md)|Modifies a TDrawingText&#8203;Properties by adding the settings from a TFxFont\.<br />|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both strings are the same, and 1 if obj is smaller than this\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same string and formatting\.<br />|
|[DrawingHAlign&#8203;From&#8203;Align](DrawingHAlignFromAlign.md)|Converts a horizontal alignment from Excel alignment to Drawing alignment\.<br />|
|[ReplaceParagraph](ReplaceParagraph.md)|Returns a new rich string with one paragraph of the original rich string replaced\.<br />|
|[WithNewFieldIds](WithNewFieldIds.md)|Returns a new TDrawingRichString with new field ids if the DrawingRichString has field ids\.<br />While FlexCel will do this automatically when you link a shape, you can use this method when creating a new linked shape that requires new field ids\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[Addition](op_Addition.md)|Adapts the \+ operator so it can add two instances of this record\.|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from string to TDrawingRichString](op_Implicit.md#implicit-conversion-from-string-to-tdrawingrichstring)<br />  [Implicit conversion from TDrawingRichString to string](op_Implicit.md#implicit-conversion-from-tdrawingrichstring-to-string)<br />|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|


## Properties

|Name|Description|
|---|---|
|[Value](Value.md)|Text of the string without formatting\. Might be null\.<br />|
|[ParagraphCount](ParagraphCount.md)|The count of Paragraphs in this string\.<br />|
|[Length](Length.md)|Length of the DrawingRichString\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the string has no data\.<br />|



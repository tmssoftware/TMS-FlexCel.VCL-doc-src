---
uid: TDrawingTextRun
description: TDrawingTextRun
---

# TDrawingTextRun Record

A rich formatting run used in text inside of a drawing\. This struct is immutable\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDrawingTextRun = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[CompareTo](CompareTo.md)|Returns \-1 if obj is bigger than this, 0 if both strings are the same, and 1 if obj is smaller than this\.<br />|
|[Create](Create.md)|Creates a new Text Run with some text\.<br />|
|[CreateField](CreateField.md)|Creates a new Text Run with a field\.<br />|
|[Equals](Equals.md)|Returns true if both instances have the same string and formatting\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[ToString](ToString.md)|String in the text run\.<br />|
|[WithNewFieldId](WithNewFieldId.md)|Returns a new TDrawingTextRun with new field ids if the DrawingTextRun has field ids\.<br />While FlexCel will do this automatically when you link a shape, you can use this method when creating a new linked shape that requires new field ids\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[GreaterThan](op_GreaterThan.md)|Adapts the > operator so it returns true when the first parameter is bigger than the second\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[LessThan](op_LessThan.md)|Adapts the \< operator so it returns true when the first parameter is smaller than the second\.|


## Properties

|Name|Description|
|---|---|
|[FieldId](FieldId.md)|Id for the Field that this text run holds\. It must be an unique GUID per field which has different linked cells\.<br />Two shapes with the same linked cell can share the same FieldId\.<br />|
|[FieldName](FieldName.md)|Field that this text run holds\. If empty, then this run holds text and not a field\.<br />|
|[IsBreak](IsBreak.md)|Returns true if this run contains a single line break\.<br />|
|[IsFieldName](IsFieldName.md)|If true, this run contains a field name and not text\.<br />|
|[Text](Text.md)|String that this text run holds\. If this run holds a field, the text should be ignored\.<br />|
|[TextProperties](TextProperties.md)|Properties for this text run\.<br />|



---
uid: TObjectTextProperties
description: TObjectTextProperties
---

# TObjectTextProperties Class

Specifies properties for the text in an autoshape or object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TObjectTextProperties = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tobjecttextpropertiescreate)<br />  [Create\(Boolean, THFlxAlignment, TVFlxAlignment, TTextRotation\)](Create.md#tobjecttextpropertiescreateboolean-thflxalignment-tvflxalignment-ttextrotation)<br />|


## Methods

|Name|Description|
|---|---|
|[EqualValues](EqualValues.md)|Returns true if both instances of the objects contain the same values\. Instances might be different, this method will return if their values are equal\. Instances can be null\.<br />|
|[Clone](Clone.md)|Creates a new object that is a copy of the current instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[LockText](LockText.md)|Specifies if the text of the object is locked\.<br />|
|[HAlignment](HAlignment.md)|Horizontal alignment for the text in the object\.<br /><br />**Important:** This property uses xls, not xlsx semantics, because it is used in comments which follow xls semantics even in xlsx files\. For more information see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)|
|[VAlignment](VAlignment.md)|Horizontal alignment for the text in the object\.<br /><br />**Important:** This property uses xls, not xlsx semantics, because it is used in comments which follow xls semantics even in xlsx files\. For more information see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)|
|[TextRotation](TextRotation.md)|Determines how the text is oriented in the object\.<br /><br />**Important:** This property uses xls, not xlsx semantics, because it is used in comments which follow xls semantics even in xlsx files\. For more information see [Text Rotation In Xls And Xlsx](xref:TextRotationInXlsAndXlsx)|



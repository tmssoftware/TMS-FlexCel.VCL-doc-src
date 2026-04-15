---
uid: TCustomXmlPart
description: TCustomXmlPart
---

# TCustomXmlPart Record

Implements a custom XML part as described in [https://msdn.microsoft.com/en-us/library/bb608618.aspx](https://msdn.microsoft.com/en-us/library/bb608618.aspx)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCustomXmlPart = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tcustomxmlpartcreate)<br />  [Create\(string, TArray\<string>\)](Create.md#tcustomxmlpartcreatestring-tarraystring)<br />  [Create\(TGUID, string, TArray\<string>\)](Create.md#tcustomxmlpartcreatetguid-string-tarraystring)<br />|
|[Equals](Equals.md)|Returns true if both objects have the same contents\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode for the object\.<br />|
|[Clone](Clone.md)|Returns a deep copy of the object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Id](Id.md)|Id of the part\. This must be an unique identifier\.<br />|
|[Xml](Xml.md)|Xml content of the part\.<br />|
|[Schemas](Schemas.md)|A list of schemas associated with the part\. When you set this value the array will be cloned, so you can then modify the original array and it won't modify the part\.<br />|



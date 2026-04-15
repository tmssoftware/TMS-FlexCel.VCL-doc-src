---
uid: TDocumentCustomProperty
description: TDocumentCustomProperty
---

# TDocumentCustomProperty Record

Encapsulates a custom property of an Excel file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDocumentCustomProperty = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string, string, Integer, string, TDocumentCustomPropertyType, string\)](Create.md#tdocumentcustompropertycreatestring-string-integer-string-tdocumentcustompropertytype-string)<br />  [Create\(string, string, Integer, string, TDocumentCustomPropertyType, string, string\)](Create.md#tdocumentcustompropertycreatestring-string-integer-string-tdocumentcustompropertytype-string-string)<br />|
|[Equals](Equals.md)|Returns true if 2 objects have the same data\.<br />|
|[GetHashCode](GetHashCode.md)|The hashcode of the object\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name of the custom property\.<br />|
|[FmtId](FmtId.md)|GUID for the property\. In Excel this value is always \{&#8203;D5CDD505\-&#8203;2E9C\-&#8203;101B\-&#8203;9397\-&#8203;08002B2CF9AE\} You can leave this null, in this case \{&#8203;D5CDD505\-&#8203;2E9C\-&#8203;101B\-&#8203;9397\-&#8203;08002B2CF9AE\} will be used\.<br />|
|[PId](PId.md)|Numeric Id for the property\. This value is for OLE compatibility and must be unique\.<br />|
|[LinkTarget](LinkTarget.md)|Specifies the name of a bookmark in the  table or named cell from which the value of this custom document  property should be extracted\. You can normally leave this value null\.<br />|
|[PropType](PropType.md)|Type of the property\. Note that while you can define any variant, Excel only recognizes the types in this enumeration\.<br />|
|[Value](Value.md)|Value of the property\. You must ensure it is valid for the proptype\.<br />|
|[PropTypeStr](PropTypeStr.md)|Used for unknown prop types, it handles the string with the name\. You shouldn't need to use this\.<br />|
|[Empty](Empty.md)|Returns an empty property|



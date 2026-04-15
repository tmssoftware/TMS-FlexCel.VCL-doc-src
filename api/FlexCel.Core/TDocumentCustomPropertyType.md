---
uid: TDocumentCustomPropertyType
description: TDocumentCustomPropertyType
---

# TDocumentCustomPropertyType Enumeration

Defines which kind of property is a custom property\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|String|0|property is a string\.<br />|
|Double|1|Property is a double\.<br />|
|Long|2|Property is a long\.<br />|
|Boolean|3|Property is a boolean\.<br />|
|DateTime|4|Property is a date time\.<br />|
|Blob|5|Property is a byte array\. The byte array is encoded in base64\.<br />|
|Unknown|6|The property is something else\. Note that Excel won't recognize properties with other data types than the ones in this enumeration, but you can write any variant as a custom property\.<br />When the type is unknown, the real type is stored in the PropTypeStr field\.<br />|



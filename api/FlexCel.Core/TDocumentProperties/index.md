---
uid: TDocumentProperties
description: TDocumentProperties
---

# TDocumentProperties Class

Properties for an Excel sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDocumentProperties = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TDocumentProperties instance and initializes it\.<br />|


## Methods

|Name|Description|
|---|---|
|[GetStandardProperty](GetStandardProperty.md)|Returns a standard document property \(Like Author, Title, etc\.\)\. This method returns an object that might be:[...[more]](GetStandardProperty.md)|
|[GetUsedStandard&#8203;Properties](GetUsedStandardProperties.md)|Returns a list of all the standard properties that are set\.<br />|
|[SetStandardProperty](SetStandardProperty.md)|This method only works in **xlsx** files\. It will set the standard property with the given Id to the specified value\. Set the value to null or empty to clear the property\.<br />|
|[GetCustomProperty](GetCustomProperty.md)|Returns a custom property with a given name\.<br />|
|[SetCustomProperty](SetCustomProperty.md)|This method only works in **xlsx** files\. Sets a custom property with a given name\. Set the value to null or empty string to remove the property\.<br />|
|[GetAllCustom&#8203;Properties](GetAllCustomProperties.md)|Returns a list of all the names of custom properties in the file\.<br />|
|[RemoveAllProperties](RemoveAllProperties.md)|This method will remove all document properties of the file\. You can use it to be sure you aren't embedding any confidential information on the properties\.<br />|


## Properties

|Name|Description|
|---|---|
|[PreserveCreationDate](PreserveCreationDate.md)|By default FlexCel will set the creation date in the file to be the date when you actually created it, no matter the value originally stored in the file\.<br />This assumes you are starting from a template and generating a new document from it\.<br />But if you are modifying an existing file and want to preserve the original creation date, then you need to set this property to true\. **Note that this property sets itself automatically to true if you manually set the creation time of a file\.<br />**|
|[PreserveModifiedDate](PreserveModifiedDate.md)|By default FlexCel will set the modified date in the file to be the date when you actually saved it, no matter the value originally stored in the file\.<br />But if you need to set a different modified date than the date in the server, or you don't want a new modified date to be saved and preserve the one in the document,  then you need to set this property to true\.<br />If you are setting this property to true, you probably also want to set [PreserveCreationDate](PreserveCreationDate.md) to true\.<br />**Note that this property sets itself automatically to true if you manually set the modified time of a file\.<br />**|



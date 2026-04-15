---
uid: TDocumentProperties.GetStandardProperty
description: TDocumentProperties.GetStandardProperty
---

# TDocumentProperties\.GetStandardProperty Method

Returns a standard document property \(Like Author, Title, etc\.\)\. This method returns an object that might be:
* **null**: If the property is not assigned\.
* **Int16, Int32, Int64, Single, Double, Decimal**: If the property is a number\.
* **DateTime**: If the property is a Date or a DateTime\.
* **String**: If the property is a string\.
* **Boolean**: If the property is a boolean\.
* **An array of byte \(byte\[\]\)**: If the property is a Blob\.
* **An array of object \(object\[\]\)**: If the property is an array\. Each one of the members of the array must be of one of the types specified here\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TDocumentProperties/index.md">TDocumentProperties</a>.GetStandardProperty(const PropertyId: <a href="../TPropertyId.md">TPropertyId</a>): string;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**PropertyId**|[TPropertyId](../TPropertyId.md)||


## See also

* [TDocumentProperties](../TDocumentProperties/index.md)


---
uid: TDocumentProperties.SetCustomProperty
description: TDocumentProperties.SetCustomProperty
---

# TDocumentProperties\.SetCustomProperty Method

This method only works in **xlsx** files\. Sets a custom property with a given name\. Set the value to null or empty string to remove the property\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TDocumentProperties/index.md">TDocumentProperties</a>.SetCustomProperty(const name: string; const proptype: <a href="../TDocumentCustomPropertyType.md">TDocumentCustomPropertyType</a>; const value: string; const propertyId: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name of the custom property you want to create or modify\.|
|const|**proptype**|[TDocumentCustom&#8203;Property&#8203;Type](../TDocumentCustomPropertyType.md)|Type of the property \(boolean, string, etc\.\)|
|const|**value**|string|Value for the property\. Note that while it is a string, it must be convertible  to the type you are specifying\. Doubles should use "\." as decimal separators\.|
|const|**propertyId**|Integer|Numeric Id for the property\. This value must be unique and **bigger or equal to 2**\.|


## See also

* [TDocumentProperties](../TDocumentProperties/index.md)


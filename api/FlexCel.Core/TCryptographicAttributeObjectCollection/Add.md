---
uid: TCryptographicAttributeObjectCollection.Add
description: TCryptographicAttributeObjectCollection.Add
---

# TCryptographicAttributeObjectCollection\.Add Method

## Overloads

* [TCryptographicAttributeObjectCollection\.Add\(TAsnEncodedData\)](#tcryptographicattributeobjectcollectionaddtasnencodeddata)
* [TCryptographicAttributeObjectCollection\.Add\(TCryptographicAttributeObject\)](#tcryptographicattributeobjectcollectionaddtcryptographicattributeobject)

# TCryptographicAttributeObjectCollection\.Add\(TAsnEncodedData\)
Adds a value to the list\. If there is already an attribute with the same oid, the value is added to it, and if there isn't, a new attribute is created for the value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TCryptographicAttributeObjectCollection/index.md">TCryptographicAttributeObjectCollection</a>.Add(const aValue: <a href="../TAsnEncodedData/index.md">TAsnEncodedData</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|[TAsnEncodedData](../TAsnEncodedData/index.md)||


## See also

* [TCryptographicAttributeObjectCollection](../TCryptographicAttributeObjectCollection/index.md)

# TCryptographicAttributeObjectCollection\.Add\(TCryptographicAttributeObject\)
Adds an attribute to the list\. **The list takes ownership of the attribute** and will free it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TCryptographicAttributeObjectCollection/index.md">TCryptographicAttributeObjectCollection</a>.Add(const aAttribute: <a href="../TCryptographicAttributeObject/index.md">TCryptographicAttributeObject</a>); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aAttribute**|[TCryptographic&#8203;Attribute&#8203;Object](../TCryptographicAttributeObject/index.md)||


## See also

* [TCryptographicAttributeObjectCollection](../TCryptographicAttributeObjectCollection/index.md)


---
uid: TLookupFieldDefinition.Create
description: TLookupFieldDefinition.Create
---

# TLookupFieldDefinition\.Create Method

Creates a new lookupfield definition\. Fields will be copied\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TLookupFieldDefinition/index.md">TLookupFieldDefinition</a>.Create(const aKeyFields: TArray&lt;Int32>; const aResultField: Integer; const aOriginalKeyFieldsDefinition: string): <a href="../TLookupFieldDefinition/index.md">TLookupFieldDefinition</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aKeyFields**|TArray\<Int32>|A list of fields to be used in the key\. The array will be copied so you can reuse it\.|
|const|**aResultField**|Integer|The field to be returned from the lookup\.|
|const|**aOriginalKeyFieldsDefinition**|string|The key fields definition as it is written in the lookup tag\. You will normally not need this data\.|


## See also

* [TLookupFieldDefinition](../TLookupFieldDefinition/index.md)


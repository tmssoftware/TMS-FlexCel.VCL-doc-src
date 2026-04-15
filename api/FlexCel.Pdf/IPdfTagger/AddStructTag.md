---
uid: IPdfTagger.AddStructTag
description: IPdfTagger.AddStructTag
---

# IPdfTagger\.AddStructTag Method

Adds a new tag to the structure tree\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IPdfTagger/index.md">IPdfTagger</a>.AddStructTag(const objId: Integer; const parentObjId: Integer; const childrenObjIds: TEnumerable&lt;Integer&gt;; const name: string; const altText: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objId**|Integer|Id of the object being inserted\. Get a value with [GetObjectIds](GetObjectIds.md)|
|const|**parentObjId**|Integer|Id of the object which is parent to this one, in order to create the tag tree\.<br />Use a negative number if the tag derives directly from the root\.|
|const|**childrenObjIds**|TEnumerable\<Integer>|A list of the children tags, to create the Tag tree\.|
|const|**name**|string|Name of the tag\.|
|const|**altText**|string|Alt text for the tag, if applicable\. Use null or empty if there is no Alt text\.|


## See also

* [IPdfTagger](../IPdfTagger/index.md)


---
uid: IPdfPageTagger.AddContentTag
description: IPdfPageTagger.AddContentTag
---

# IPdfPageTagger\.AddContentTag Method

Adds a new tag to the structure tree, with a child which was added with TagContentBegin/TagContentEnd\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IPdfPageTagger/index.md">IPdfPageTagger</a>.AddContentTag(const objId: Integer; const parentObjId: Integer; const childMcId: Integer; const name: string; const altText: string); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objId**|Integer|Id of the object being inserted\. Get a value with GetObjectIds\(int\)|
|const|**parentObjId**|Integer|Id of the object which is parent to this one, in order to create the tag tree\.<br />Use a negative number if the tag derives directly from the root\.|
|const|**childMcId**|Integer|The id used in TagContentBegin/TagContentEnd\.|
|const|**name**|string|Name of the tag\.|
|const|**altText**|string|Alt text for the tag, if applicable\. Use null or empty if there is no Alt text\.|


## See also

* [IPdfPageTagger](../IPdfPageTagger/index.md)


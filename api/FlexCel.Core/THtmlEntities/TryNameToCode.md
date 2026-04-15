---
uid: THtmlEntities.TryNameToCode
description: THtmlEntities.TryNameToCode
---

# THtmlEntities\.TryNameToCode Method

Converts an Html entity like "amp" into the unicode code for the character\. The input string can also  be a \# code, in decimal or hexadecimal\. \(for example &amp;\#64\)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../THtmlEntities/index.md">THtmlEntities</a>.TryNameToCode(const EntityName: string; out Code: Integer): Boolean; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**EntityName**|string|Name of the entity without the starting "&amp;" and the trailing ";"|
|out|**Code**|Integer|Unicode representation of the entity\.|


## Returns

True if the code exists, false otherwise\.

## See also

* [THtmlEntities](../THtmlEntities/index.md)


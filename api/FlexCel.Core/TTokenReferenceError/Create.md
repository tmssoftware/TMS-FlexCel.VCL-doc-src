---
uid: TTokenReferenceError.Create
description: TTokenReferenceError.Create
---

# TTokenReferenceError\.Create Constructor

Creates a new TTokenError instance with the corresponding error type\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TTokenReferenceError/index.md">TTokenReferenceError</a>.Create(const aIsArea: Boolean; const aIs3D: Boolean; const aIsRelative: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aIsArea**|Boolean|If true this is a reference to an area, else to a cell\.|
|const|**aIs3D**|Boolean|If true this is a 3d reference, else it is a normal 2D reference\.|
|const|**aIsRelative**|Boolean|If true this reference is relative to the cell where the formula is\.|


## See also

* [TTokenReferenceError](../TTokenReferenceError/index.md)


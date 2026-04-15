---
uid: IEmbeddedObjects.GetObjectProperties
description: IEmbeddedObjects.GetObjectProperties
---

# IEmbeddedObjects\.GetObjectProperties Method

Returns information on an object and all of its children\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>.GetObjectProperties(const objectIndex: Integer; const GetShapeOptions: Boolean): <a href="../IShapeProperties/index.md">IShapeProperties</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**GetShapeOptions**|Boolean|When true, shape options will be retrieved\. As this can be a slow operation, only specify true when you really need those options\.|


## See also

* [IEmbeddedObjects](../IEmbeddedObjects/index.md)


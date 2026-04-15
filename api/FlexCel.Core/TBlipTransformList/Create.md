---
uid: TBlipTransformList.Create
description: TBlipTransformList.Create
---

# TBlipTransformList\.Create Constructor

## Overloads

* [TBlipTransformList\.Create\(Integer\)](#tbliptransformlistcreateinteger)
* [TBlipTransformList\.Create\(TBlipTransformArray, Boolean\)](#tbliptransformlistcreatetbliptransformarray-boolean)

# TBlipTransformList\.Create\(Integer\)
Creates a new TBlipTransformList with the given number of elements\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBlipTransformList/index.md">TBlipTransformList</a>.Create(const listLength: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**listLength**|Integer|Number of elements in the list\.|


## See also

* [TBlipTransformList](../TBlipTransformList/index.md)

# TBlipTransformList\.Create\(TBlipTransformArray, Boolean\)
Creates a new blip transform list from an existing array of bliptransforms\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBlipTransformList/index.md">TBlipTransformList</a>.Create(const aTransforms: <a href="../TBlipTransform/index.md">TArray&lt;TBlipTransform></a>; const copyTransforms: Boolean);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTransforms**|[TArray\<&#8203;TBlip&#8203;Transform>](../TBlipTransform/index.md)|Array with the bliptransforms\.|
|const|**copyTransforms**|Boolean|If true, the transforms will be copied into the list, else the array will be assigned to the list|


## See also

* [TBlipTransformList](../TBlipTransformList/index.md)


---
uid: TTableApplyBorders.Create
description: TTableApplyBorders.Create
---

# TTableApplyBorders\.Create Method

## Overloads

* [TTableApplyBorders\.Create\(Boolean\)](#ttableapplyborderscreateboolean)
* [TTableApplyBorders\.Create\(Boolean, Boolean, Boolean, Boolean, Boolean, Boolean\)](#ttableapplyborderscreateboolean-boolean-boolean-boolean-boolean-boolean)

# TTableApplyBorders\.Create\(Boolean\)
Creates an Apply Borders setting all members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyBorders/index.md">TTableApplyBorders</a>.Create(const AllTrue: Boolean): <a href="../TTableApplyBorders/index.md">TTableApplyBorders</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**AllTrue**|Boolean|If true all members will be set to true\. If not, all members will be false\.|


## See also

* [TTableApplyBorders](../TTableApplyBorders/index.md)

# TTableApplyBorders\.Create\(Boolean, Boolean, Boolean, Boolean, Boolean, Boolean\)
Creates a new struct setting the members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyBorders/index.md">TTableApplyBorders</a>.Create(const aLeft: Boolean; const aTop: Boolean; const aRight: Boolean; const aBottom: Boolean; const aInsideVertical: Boolean; const aInsideHorizontal: Boolean): <a href="../TTableApplyBorders/index.md">TTableApplyBorders</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aLeft**|Boolean|If true, the left border will be applied\.|
|const|**aTop**|Boolean|If true, the top border will be applied\.|
|const|**aRight**|Boolean|If true, the right border will be applied\.|
|const|**aBottom**|Boolean|If true, the bottom border will be applied\.|
|const|**aInsideVertical**|Boolean|If true, the inside vertical borders will be applied\.|
|const|**aInsideHorizontal**|Boolean|If true, the inside horizontal borders will be applied\.|


## See also

* [TTableApplyBorders](../TTableApplyBorders/index.md)


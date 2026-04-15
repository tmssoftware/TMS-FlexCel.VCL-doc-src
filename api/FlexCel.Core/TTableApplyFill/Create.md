---
uid: TTableApplyFill.Create
description: TTableApplyFill.Create
---

# TTableApplyFill\.Create Method

## Overloads

* [TTableApplyFill\.Create\(Boolean\)](#ttableapplyfillcreateboolean)
* [TTableApplyFill\.Create\(Boolean, Boolean, Boolean\)](#ttableapplyfillcreateboolean-boolean-boolean)

# TTableApplyFill\.Create\(Boolean\)
Creates an Apply Fill setting all members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyFill/index.md">TTableApplyFill</a>.Create(const AllTrue: Boolean): <a href="../TTableApplyFill/index.md">TTableApplyFill</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**AllTrue**|Boolean|If true all members will be set to true\. If not, all members will be false\.|


## See also

* [TTableApplyFill](../TTableApplyFill/index.md)

# TTableApplyFill\.Create\(Boolean, Boolean, Boolean\)
Creates a new struct setting the members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyFill/index.md">TTableApplyFill</a>.Create(const aStyle: Boolean; const aFgColor: Boolean; const aBgColor: Boolean): <a href="../TTableApplyFill/index.md">TTableApplyFill</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStyle**|Boolean|If true, the style will be applied\.|
|const|**aFgColor**|Boolean|If true, the foreground color will be applied\.|
|const|**aBgColor**|Boolean|If true, the background color will be applied\.|


## See also

* [TTableApplyFill](../TTableApplyFill/index.md)


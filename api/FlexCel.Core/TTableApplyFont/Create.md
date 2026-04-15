---
uid: TTableApplyFont.Create
description: TTableApplyFont.Create
---

# TTableApplyFont\.Create Method

## Overloads

* [TTableApplyFont\.Create\(Boolean\)](#ttableapplyfontcreateboolean)
* [TTableApplyFont\.Create\(Boolean, Boolean, Boolean, Boolean\)](#ttableapplyfontcreateboolean-boolean-boolean-boolean)

# TTableApplyFont\.Create\(Boolean\)
Creates an Apply Font setting all members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyFont/index.md">TTableApplyFont</a>.Create(const AllTrue: Boolean): <a href="../TTableApplyFont/index.md">TTableApplyFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**AllTrue**|Boolean|If true all members will be set to true\. If not, all members will be false\.|


## See also

* [TTableApplyFont](../TTableApplyFont/index.md)

# TTableApplyFont\.Create\(Boolean, Boolean, Boolean, Boolean\)
Creates a new struct setting the members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TTableApplyFont/index.md">TTableApplyFont</a>.Create(const aColor: Boolean; const aBoldAndItalic: Boolean; const aStrikeout: Boolean; const aUnderline: Boolean): <a href="../TTableApplyFont/index.md">TTableApplyFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aColor**|Boolean|If true, the font color will be applied\.|
|const|**aBoldAndItalic**|Boolean|If true, the font bold and italic styles will be applied\.|
|const|**aStrikeout**|Boolean|If true, the font strikeout style will be applied\.|
|const|**aUnderline**|Boolean|If true, the font underline will be applied\.|


## See also

* [TTableApplyFont](../TTableApplyFont/index.md)


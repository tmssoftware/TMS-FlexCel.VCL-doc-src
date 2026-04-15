---
uid: TCondFmtApplyFont.Create
description: TCondFmtApplyFont.Create
---

# TCondFmtApplyFont\.Create Method

## Overloads

* [TCondFmtApplyFont\.Create\(Boolean\)](#tcondfmtapplyfontcreateboolean)
* [TCondFmtApplyFont\.Create\(Boolean, Boolean, Boolean, Boolean, Boolean, Boolean\)](#tcondfmtapplyfontcreateboolean-boolean-boolean-boolean-boolean-boolean)

# TCondFmtApplyFont\.Create\(Boolean\)
Creates an Apply Font setting all members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCondFmtApplyFont/index.md">TCondFmtApplyFont</a>.Create(const AllTrue: Boolean): <a href="../TCondFmtApplyFont/index.md">TCondFmtApplyFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**AllTrue**|Boolean|If true all members will be set to true\. If not, all members will be false\.|


## See also

* [TCondFmtApplyFont](../TCondFmtApplyFont/index.md)

# TCondFmtApplyFont\.Create\(Boolean, Boolean, Boolean, Boolean, Boolean, Boolean\)
Creates a new struct setting the members to true or false\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TCondFmtApplyFont/index.md">TCondFmtApplyFont</a>.Create(const aSize20: Boolean; const aColor: Boolean; const aBoldAndItalic: Boolean; const aStrikeout: Boolean; const aSubSuperscript: Boolean; const aUnderline: Boolean): <a href="../TCondFmtApplyFont/index.md">TCondFmtApplyFont</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSize20**|Boolean|If true, the font size will be applied\.|
|const|**aColor**|Boolean|If true, the font color will be applied\.|
|const|**aBoldAndItalic**|Boolean|If true, the font bold and italic styles will be applied\.|
|const|**aStrikeout**|Boolean|If true, the font strikeout style will be applied\.|
|const|**aSubSuperscript**|Boolean|If true, the font subscript and superscript will be applied\.|
|const|**aUnderline**|Boolean|If true, the font underline will be applied\.|


## See also

* [TCondFmtApplyFont](../TCondFmtApplyFont/index.md)


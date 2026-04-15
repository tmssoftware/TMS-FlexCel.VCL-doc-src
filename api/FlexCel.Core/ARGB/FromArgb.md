---
uid: ARGB.FromArgb
description: ARGB.FromArgb
---

# ARGB\.FromArgb Method

## Overloads

* [ARGB\.FromArgb\(Integer\)](#argbfromargbinteger)
* [ARGB\.FromArgb\(Integer, TUIColor\)](#argbfromargbinteger-tuicolor)
* [ARGB\.FromArgb\(Integer, Integer, Integer\)](#argbfromargbinteger-integer-integer)
* [ARGB\.FromArgb\(Integer, Integer, Integer, Integer\)](#argbfromargbinteger-integer-integer-integer)

# ARGB\.FromArgb\(Integer\)
Returns a color from an integer\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../ARGB/index.md">ARGB</a>.FromArgb(const aValue: Integer): <a href="../TUIColor/index.md">TUIColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|Integer|Value as AARRGGBB|


## See also

* [ARGB](../ARGB/index.md)

# ARGB\.FromArgb\(Integer, TUIColor\)
Returns a color base in other color but with a different transparency\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../ARGB/index.md">ARGB</a>.FromArgb(const alpha: Integer; const aColor: <a href="../TUIColor/index.md">TUIColor</a>): <a href="../TUIColor/index.md">TUIColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**alpha**|Integer|Alpha value for the new color \(between 0 and 255\)|
|const|**aColor**|[TUIColor](../TUIColor/index.md)|Source color\.|


## See also

* [ARGB](../ARGB/index.md)

# ARGB\.FromArgb\(Integer, Integer, Integer\)
Creates a color from Red, Green and Blue components without transparency\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../ARGB/index.md">ARGB</a>.FromArgb(const red: Integer; const green: Integer; const blue: Integer): <a href="../TUIColor/index.md">TUIColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**red**|Integer|Red component, between 0 and 255\.|
|const|**green**|Integer|Red component, between 0 and 255\.|
|const|**blue**|Integer|Blue component, between 0 and 255\.|


## See also

* [ARGB](../ARGB/index.md)

# ARGB\.FromArgb\(Integer, Integer, Integer, Integer\)
Creates a color from Red, Green and Blue components with transparency\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../ARGB/index.md">ARGB</a>.FromArgb(const alpha: Integer; const red: Integer; const green: Integer; const blue: Integer): <a href="../TUIColor/index.md">TUIColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**alpha**|Integer|Alpha component, between 0 \(completely transparent\) and 255 \(completely opaque\)\.|
|const|**red**|Integer|Red component, between 0 and 255\.|
|const|**green**|Integer|Red component, between 0 and 255\.|
|const|**blue**|Integer|Blue component, between 0 and 255\.|


## See also

* [ARGB](../ARGB/index.md)


---
uid: TSpinProperties.Create
description: TSpinProperties.Create
---

# TSpinProperties\.Create Method

## Overloads

* [TSpinProperties\.Create](#tspinpropertiescreate)
* [TSpinProperties\.Create\(Integer, Integer, Integer, Integer\)](#tspinpropertiescreateinteger-integer-integer-integer)
* [TSpinProperties\.Create\(Integer, Integer, Integer, Integer, Integer\)](#tspinpropertiescreateinteger-integer-integer-integer-integer)
* [TSpinProperties\.Create\(Integer, Integer, Integer, Integer, Integer, Boolean\)](#tspinpropertiescreateinteger-integer-integer-integer-integer-boolean)

# TSpinProperties\.Create
Creates an empty TSpinProperties instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSpinProperties/index.md">TSpinProperties</a>.Create: <a href="../TSpinProperties/index.md">TSpinProperties</a>; static; overload;</code></pre>

## See also

* [TSpinProperties](../TSpinProperties/index.md)

# TSpinProperties\.Create\(Integer, Integer, Integer, Integer\)
Creates a new instance with data and a default dx of 16\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSpinProperties/index.md">TSpinProperties</a>.Create(const aMin: Integer; const aMax: Integer; const aIncr: Integer; const aPage: Integer): <a href="../TSpinProperties/index.md">TSpinProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Integer|Minimum value for the spin control\.|
|const|**aMax**|Integer|Maximum value for the spin control\.|
|const|**aIncr**|Integer|Small increment\.|
|const|**aPage**|Integer|Big increment\.|


## See also

* [TSpinProperties](../TSpinProperties/index.md)

# TSpinProperties\.Create\(Integer, Integer, Integer, Integer, Integer\)
Creates a new instance with data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSpinProperties/index.md">TSpinProperties</a>.Create(const aMin: Integer; const aMax: Integer; const aIncr: Integer; const aPage: Integer; const aDx: Integer): <a href="../TSpinProperties/index.md">TSpinProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Integer|Minimum value for the spin control\.|
|const|**aMax**|Integer|Maximum value for the spin control\.|
|const|**aIncr**|Integer|Small increment\.|
|const|**aPage**|Integer|Big increment\.|
|const|**aDx**|Integer|Width of the scrollbar\. It should normally be 16\.|


## See also

* [TSpinProperties](../TSpinProperties/index.md)

# TSpinProperties\.Create\(Integer, Integer, Integer, Integer, Integer, Boolean\)
Creates a new instance with data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSpinProperties/index.md">TSpinProperties</a>.Create(const aMin: Integer; const aMax: Integer; const aIncr: Integer; const aPage: Integer; const aDx: Integer; const aHorizontal: Boolean): <a href="../TSpinProperties/index.md">TSpinProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aMin**|Integer|Minimum value for the spin control\.|
|const|**aMax**|Integer|Maximum value for the spin control\.|
|const|**aIncr**|Integer|Small increment\.|
|const|**aPage**|Integer|Big increment\.|
|const|**aDx**|Integer|Width of the scrollbar\. It should normally be 16\.|
|const|**aHorizontal**|Boolean|If true, the spin control will be oriented horizontally\.|


## See also

* [TSpinProperties](../TSpinProperties/index.md)


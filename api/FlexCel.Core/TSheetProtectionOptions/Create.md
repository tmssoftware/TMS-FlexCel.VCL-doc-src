---
uid: TSheetProtectionOptions.Create
description: TSheetProtectionOptions.Create
---

# TSheetProtectionOptions\.Create Method

## Overloads

* [TSheetProtectionOptions\.Create](#tsheetprotectionoptionscreate)
* [TSheetProtectionOptions\.Create\(Boolean\)](#tsheetprotectionoptionscreateboolean)
* [TSheetProtectionOptions\.Create\(TProtectionType\)](#tsheetprotectionoptionscreatetprotectiontype)

# TSheetProtectionOptions\.Create
Initializes a not protected block\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>.Create: <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>; static; overload;</code></pre>

## See also

* [TSheetProtectionOptions](../TSheetProtectionOptions/index.md)

# TSheetProtectionOptions\.Create\(Boolean\)
Creates a protected or unprotected sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>.Create(const allTrue: Boolean): <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**allTrue**|Boolean|If true, all properties on this class will be set to true\.<br />This means cells on the sheet will be protected, and things like Cell formatting will be not\.<br />If false, all properties will be set to false\.|


## See also

* [TSheetProtectionOptions](../TSheetProtectionOptions/index.md)

# TSheetProtectionOptions\.Create\(TProtectionType\)
Creates a protected or unprotected sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>.Create(const protectAll: <a href="../TProtectionType.md">TProtectionType</a>): <a href="../TSheetProtectionOptions/index.md">TSheetProtectionOptions</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**protectAll**|[TProtectionType](../TProtectionType.md)|If true, all things in the sheet will be protected\. this means a property like [Contents](Contents.md)  will be true, and others like [CellFormatting](CellFormatting.md)  will be false\.<br />If false, nothing will\.|


## See also

* [TSheetProtectionOptions](../TSheetProtectionOptions/index.md)


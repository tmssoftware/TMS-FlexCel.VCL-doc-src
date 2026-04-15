---
uid: TExcelColor.FromArgb
description: TExcelColor.FromArgb
---

# TExcelColor\.FromArgb Method

## Overloads

* [TExcelColor\.FromArgb\(Integer\)](#texcelcolorfromargbinteger)
* [TExcelColor\.FromArgb\(Integer, Double\)](#texcelcolorfromargbinteger-double)
* [TExcelColor\.FromArgb\(Byte, Byte, Byte\)](#texcelcolorfromargbbyte-byte-byte)
* [TExcelColor\.FromArgb\(Byte, Byte, Byte, Double\)](#texcelcolorfromargbbyte-byte-byte-double)

# TExcelColor\.FromArgb\(Integer\)
Returns a Color class with the specified rgb color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromArgb(const argb: Integer): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**argb**|Integer|Color to set\.|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.FromArgb\(Integer, Double\)
Returns a Color class with the specified rgb color and with the specified tint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromArgb(const argb: Integer; const tint: Double): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**argb**|Integer|Color to set\.|
|const|**tint**|Double|Tint for the color\.<br /><br /><br /><br /><br />If you try to set a value less than \-1 it will be stored as \-1, and values bigger than 1 as 1\. No exceptions will be raised\.<br />|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.FromArgb\(Byte, Byte, Byte\)
Returns a Color class with the specified rgb color and with the 0 tint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromArgb(const r: Byte; const g: Byte; const b: Byte): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**r**|Byte|Red component of the color\.|
|const|**g**|Byte|Green component of the color\.|
|const|**b**|Byte|Blue component of the color\.|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.FromArgb\(Byte, Byte, Byte, Double\)
Returns a Color class with the specified rgb color and with the specified tint\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromArgb(const r: Byte; const g: Byte; const b: Byte; const tint: Double): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**r**|Byte|Red component of the color\.|
|const|**g**|Byte|Green component of the color\.|
|const|**b**|Byte|Blue component of the color\.|
|const|**tint**|Double|Tint for the color\.<br /><br /><br /><br /><br />If you try to set a value less than \-1 it will be stored as \-1, and values bigger than 1 as 1\. No exceptions will be raised\.<br />|


## See also

* [TExcelColor](../TExcelColor/index.md)


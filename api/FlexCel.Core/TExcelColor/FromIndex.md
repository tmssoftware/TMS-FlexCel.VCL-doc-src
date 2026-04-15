---
uid: TExcelColor.FromIndex
description: TExcelColor.FromIndex
---

# TExcelColor\.FromIndex Method

## Overloads

* [TExcelColor\.FromIndex\(Integer\)](#texcelcolorfromindexinteger)
* [TExcelColor\.FromIndex\(Integer, Double\)](#texcelcolorfromindexinteger-double)

# TExcelColor\.FromIndex\(Integer\)
Returns a color class with a specified color index\.
**For compatibility with old code, you can enter any index here\.** If the value is less than 1 or more than 56, it will assume automatic color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromIndex(const index: Integer): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index to the color palette\. \(1 based\)|


## See also

* [TExcelColor](../TExcelColor/index.md)

# TExcelColor\.FromIndex\(Integer, Double\)
Returns a color class with a specified color index\.
**For compatibility with old code, you can enter any index here\.** If the value is less than 1 or more than 56, it will assume automatic color\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelColor/index.md">TExcelColor</a>.FromIndex(const index: Integer; const tint: Double): <a href="../TExcelColor/index.md">TExcelColor</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index to the color palette\. \(1 based\)|
|const|**tint**|Double|Tint for the color\.<br /><br /><br /><br /><br />If you try to set a value less than \-1 it will be stored as \-1, and values bigger than 1 as 1\. No exceptions will be raised\.<br />|


## See also

* [TExcelColor](../TExcelColor/index.md)


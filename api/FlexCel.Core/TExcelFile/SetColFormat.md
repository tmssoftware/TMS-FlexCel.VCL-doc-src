---
uid: TExcelFile.SetColFormat
description: TExcelFile.SetColFormat
---

# TExcelFile\.SetColFormat Method

## Overloads

* [TExcelFile\.SetColFormat\(Integer, Integer\)](#texcelfilesetcolformatinteger-integer)
* [TExcelFile\.SetColFormat\(Integer, Integer, Boolean\)](#texcelfilesetcolformatinteger-integer-boolean)
* [TExcelFile\.SetColFormat\(Integer, Integer, Integer\)](#texcelfilesetcolformatinteger-integer-integer)
* [TExcelFile\.SetColFormat\(Integer, Integer, Integer, Boolean\)](#texcelfilesetcolformatinteger-integer-integer-boolean)
* [TExcelFile\.SetColFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](#texcelfilesetcolformatinteger-tflxformat-tflxapplyformat-boolean)

# TExcelFile\.SetColFormat\(Integer, Integer\)
Sets the format for an entire column\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColFormat(const col: Integer; const XF: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to set\.|
|const|**XF**|Integer|XF Format index\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColFormat\(Integer, Integer, Boolean\)
Sets the format for an entire column\. If you want to set the format for more than one column, use [SetColFormat\(Integer, Integer, Integer, Boolean\)](SetColFormat.md#texcelfilesetcolformatinteger-integer-integer-boolean) instead\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColFormat(const col: Integer; const XF: Integer; const resetColumn: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to set\.|
|const|**XF**|Integer|XF Format index\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColFormat\(Integer, Integer, Integer\)
Sets the format for a range of columns\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColFormat(const col1: Integer; const col2: Integer; const XF: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column in the range to set\.|
|const|**col2**|Integer|Last column in the range to set\.|
|const|**XF**|Integer|XF Format index\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColFormat\(Integer, Integer, Integer, Boolean\)
Sets the format for a range of columns\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColFormat(const col1: Integer; const col2: Integer; const XF: Integer; const resetColumn: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column in the range to set\.|
|const|**col2**|Integer|Last column in the range to set\.|
|const|**XF**|Integer|XF Format index\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetColFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)
Sets the format characteristics specified in ApplyFormat for the entire column\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetColFormat(const col: Integer; const newFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const applyNewFormat: <a href="../TFlxApplyFormat/index.md">TFlxApplyFormat</a>; const resetColumn: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to set\.|
|const|**newFormat**|[TFlxFormat](../TFlxFormat/index.md)|Format to apply\.|
|const|**applyNewFormat**|[TFlxApplyFormat](../TFlxApplyFormat/index.md)|Indicates which properties of newFormat will be applied to the cells\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


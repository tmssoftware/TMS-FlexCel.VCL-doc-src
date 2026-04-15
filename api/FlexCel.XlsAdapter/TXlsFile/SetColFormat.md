---
uid: TXlsFile.SetColFormat
description: TXlsFile.SetColFormat
---

# TXlsFile\.SetColFormat Method

## Overloads

* [TXlsFile\.SetColFormat\(Integer, Integer, Boolean\)](#txlsfilesetcolformatinteger-integer-boolean)
* [TXlsFile\.SetColFormat\(Integer, Integer, Integer, Boolean\)](#txlsfilesetcolformatinteger-integer-integer-boolean)
* [TXlsFile\.SetColFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](#txlsfilesetcolformatinteger-tflxformat-tflxapplyformat-boolean)

# TXlsFile\.SetColFormat\(Integer, Integer, Boolean\)
Sets the format for an entire column\. If you want to set the format for more than one column, use [TExcelFile.SetColFormat\(Integer, Integer, Integer, Boolean\)](../../FlexCel.Core/TExcelFile/SetColFormat.md#texcelfilesetcolformatinteger-integer-integer-boolean) instead\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColFormat(const col: Integer; const XF: Integer; const resetColumn: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to set\.|
|const|**XF**|Integer|XF Format index\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetColFormat\(Integer, Integer, Integer, Boolean\)
Sets the format for a range of columns\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColFormat(const col1: Integer; const col2: Integer; const XF: Integer; const resetColumn: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|First column in the range to set\.|
|const|**col2**|Integer|Last column in the range to set\.|
|const|**XF**|Integer|XF Format index\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetColFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)
Sets the format characteristics specified in ApplyFormat for the entire column\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColFormat(const col: Integer; const newFormat: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; const applyNewFormat: <a href="../../FlexCel.Core/TFlxApplyFormat/index.md">TFlxApplyFormat</a>; const resetColumn: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column to set\.|
|const|**newFormat**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Format to apply\.|
|const|**applyNewFormat**|[TFlxApplyFormat](../../FlexCel.Core/TFlxApplyFormat/index.md)|Indicates which properties of newFormat will be applied to the cells\.|
|const|**resetColumn**|Boolean|When true, all existing cells on the column will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


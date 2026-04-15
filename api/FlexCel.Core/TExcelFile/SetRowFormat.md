---
uid: TExcelFile.SetRowFormat
description: TExcelFile.SetRowFormat
---

# TExcelFile\.SetRowFormat Method

## Overloads

* [TExcelFile\.SetRowFormat\(Integer, Integer\)](#texcelfilesetrowformatinteger-integer)
* [TExcelFile\.SetRowFormat\(Integer, Integer, Boolean\)](#texcelfilesetrowformatinteger-integer-boolean)
* [TExcelFile\.SetRowFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](#texcelfilesetrowformatinteger-tflxformat-tflxapplyformat-boolean)

# TExcelFile\.SetRowFormat\(Integer, Integer\)
Sets the XF format for the entire row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowFormat(const row: Integer; const XF: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**XF**|Integer|XF format\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetRowFormat\(Integer, Integer, Boolean\)
Sets the XF format for the entire row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowFormat(const row: Integer; const XF: Integer; const resetRow: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**XF**|Integer|XF format\.|
|const|**resetRow**|Boolean|When true, all existing cells on the row will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetRowFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)
Sets the format characteristics specified in ApplyFormat for the entire row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowFormat(const row: Integer; const newFormat: <a href="../TFlxFormat/index.md">TFlxFormat</a>; const applyNewFormat: <a href="../TFlxApplyFormat/index.md">TFlxApplyFormat</a>; const resetRow: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**newFormat**|[TFlxFormat](../TFlxFormat/index.md)|Format to apply\.|
|const|**applyNewFormat**|[TFlxApplyFormat](../TFlxApplyFormat/index.md)|Indicates which properties of newFormat will be applied to the cells\.|
|const|**resetRow**|Boolean|When true, all existing cells on the row will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


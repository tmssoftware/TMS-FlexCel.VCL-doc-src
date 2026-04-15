---
uid: TXlsFile.SetRowFormat
description: TXlsFile.SetRowFormat
---

# TXlsFile\.SetRowFormat Method

## Overloads

* [TXlsFile\.SetRowFormat\(Integer, Integer, Boolean\)](#txlsfilesetrowformatinteger-integer-boolean)
* [TXlsFile\.SetRowFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)](#txlsfilesetrowformatinteger-tflxformat-tflxapplyformat-boolean)

# TXlsFile\.SetRowFormat\(Integer, Integer, Boolean\)
Sets the XF format for the entire row\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetRowFormat(const row: Integer; const XF: Integer; const resetRow: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**XF**|Integer|XF format\.|
|const|**resetRow**|Boolean|When true, all existing cells on the row will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetRowFormat\(Integer, TFlxFormat, TFlxApplyFormat, Boolean\)
Sets the format characteristics specified in ApplyFormat for the entire row\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetRowFormat(const row: Integer; const newFormat: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>; const applyNewFormat: <a href="../../FlexCel.Core/TFlxApplyFormat/index.md">TFlxApplyFormat</a>; const resetRow: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row index \(1\-based\)|
|const|**newFormat**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Format to apply\.|
|const|**applyNewFormat**|[TFlxApplyFormat](../../FlexCel.Core/TFlxApplyFormat/index.md)|Indicates which properties of newFormat will be applied to the cells\.|
|const|**resetRow**|Boolean|When true, all existing cells on the row will be reset to this format\.<br />This is the standard Excel behavior and the recommended option\. If you don't care about existing cells,  you can speed up this method by setting it to false\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.SetAutoFilter
description: TXlsFile.SetAutoFilter
---

# TXlsFile\.SetAutoFilter Method

Sets the AutoFilter in the Active sheet to point to the range specified\.
**Note: You will normally want to use [TExcelFile.SetAutoFilter\(Integer, Integer, Integer\)](../../FlexCel.Core/TExcelFile/SetAutoFilter.md#texcelfilesetautofilterinteger-integer-integer),** since that is the common way to set autofilters\. The last row shouldn't matter, so it will addapt automatically when you add rows\.
If you specify the last row, then the range will still grow to include all data, but it will include at least the last row you specify, even if it is blank\."/>

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetAutoFilter(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Row where the AutoFilter will be placed \(1 based\)\.|
|const|**col1**|Integer|First column for the AutoFilter range \(1 based\)\.|
|const|**row2**|Integer|Last row for the autofilter \(1 based\)\.|
|const|**col2**|Integer|Last column for the AutoFilter range \(1 based\)\. Note that the autofilter will automatically expand over this row if you have more non\-empty rows below this row\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


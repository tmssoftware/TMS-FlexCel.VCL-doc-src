---
uid: TXlsFile.SetColWidth
description: TXlsFile.SetColWidth
---

# TXlsFile\.SetColWidth Method

## Overloads

* [TXlsFile\.SetColWidth\(Integer, Integer\)](#txlsfilesetcolwidthinteger-integer)
* [TXlsFile\.SetColWidth\(Integer, Integer, Integer\)](#txlsfilesetcolwidthinteger-integer-integer)

# TXlsFile\.SetColWidth\(Integer, Integer\)
Sets the current Column width, in Excel internal units\. \(Character width of font 0 / 256\) Note: if possible, set many column widths at once by calling [TExcelFile.SetColWidth\(Integer, Integer, Integer\)](../../FlexCel.Core/TExcelFile/SetColWidth.md#texcelfilesetcolwidthinteger-integer-integer)\. It is faster\.
See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColWidth(const col: Integer; const width: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column index \(1 based\)|
|const|**width**|Integer|Column width, in Excel internal units\. \(Character width of font 0 / 256\)\. See [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md)|


## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.SetColWidth\(Integer, Integer, Integer\)
Sets the width of a range of columns, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColWidth(const col1: Integer; const col2: Integer; const width: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col1**|Integer|Column index of the first column in the range\. \(1 based\)|
|const|**col2**|Integer|Column index of the last column in the range\. \(1 based\)|
|const|**width**|Integer|Column width, in Excel internal units\. \(Character width of font 0 / 256\)\. See [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md)|


## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.GetColWidth
description: TXlsFile.GetColWidth
---

# TXlsFile\.GetColWidth Method

## Overloads

* [TXlsFile\.GetColWidth\(Integer\)](#txlsfilegetcolwidthinteger)
* [TXlsFile\.GetColWidth\(Integer, Boolean\)](#txlsfilegetcolwidthinteger-boolean)
* [TXlsFile\.GetColWidth\(Integer, Integer, Boolean\)](#txlsfilegetcolwidthinteger-integer-boolean)

# TXlsFile\.GetColWidth\(Integer\)
Returns the current Column width, in Excel internal units\. \(Character width of "font 0" / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColWidth(const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column Index \(1 based\)|


## Returns

Column width in internal excel units\.\(Character width of "font 0" / 256\)

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetColWidth\(Integer, Boolean\)
Returns the current Column width, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColWidth(const col: Integer; const HiddenIsZero: Boolean): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**col**|Integer|Column Index \(1 based\)|
|const|**HiddenIsZero**|Boolean|If true, the width returned for a hidden column will be 0 and not its real width\.|


## Returns

Column width in internal excel units\.\(Character width of font 0 / 256\)

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)

# TXlsFile\.GetColWidth\(Integer, Integer, Boolean\)
Returns the current Column width for a given sheet, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../../FlexCel.Core/TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetColWidth(const sheet: Integer; const col: Integer; const HiddenIsZero: Boolean): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where to look for the width\.|
|const|**col**|Integer|Column Index \(1 based\)|
|const|**HiddenIsZero**|Boolean|If true, the width returned for a hidden column will be 0 and not its real width\.|


## Returns

Column width in internal excel units\.\(Character width of font 0 / 256\)

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TExcelFile.SetAutoFilter
description: TExcelFile.SetAutoFilter
---

# TExcelFile\.SetAutoFilter Method

## Overloads

* [TExcelFile\.SetAutoFilter\(TXlsCellRange, Boolean\)](#texcelfilesetautofiltertxlscellrange-boolean)
* [TExcelFile\.SetAutoFilter\(Integer, Integer, Integer\)](#texcelfilesetautofilterinteger-integer-integer)
* [TExcelFile\.SetAutoFilter\(Integer, Integer, Integer, Integer\)](#texcelfilesetautofilterinteger-integer-integer-integer)

# TExcelFile\.SetAutoFilter\(TXlsCellRange, Boolean\)
Sets an AutoFilter in a cell range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetAutoFilter(const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const useBottomCoordinate: Boolean = False); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range to set the AutoFilter\. If range is null, this method does nothing\.|
|const|**useBottomCoordinate**|Boolean|**Optional**: Default value is False<br /><br />If false the bottom coordinate of the range will be ignored, and the range will extend until the first non\-empty row\. This is the normal way you set autofilters in Excel\.<br />When true, the range will go at least up to range\.Bottom, no matter the actual used cells in Excel\. To set an autofiter this way in Excel, you would select a range, then set the autofilter over that range\. Note that the autofilter can include rows after range\.Bottom anyway\. range\.Bottom only specifies the minimum row that must be included\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetAutoFilter\(Integer, Integer, Integer\)
Sets the AutoFilter in the Active sheet to point to the range specified\. This is the most common ways to specify autofilters, where the rows in the filter will expand to the first non\-empty row\. In the not\-common case where you want to specify a full range for the autofilter, you can use [SetAutoFilter\(Integer, Integer, Integer, Integer\)](SetAutoFilter.md#texcelfilesetautofilterinteger-integer-integer-integer)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetAutoFilter(const row: Integer; const col1: Integer; const col2: Integer); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row where the AutoFilter will be placed \(1 based\)\.|
|const|**col1**|Integer|First column for the AutoFilter range \(1 based\)\.|
|const|**col2**|Integer|Last column for the AutoFilter range \(1 based\)\.|


## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.SetAutoFilter\(Integer, Integer, Integer, Integer\)
Sets the AutoFilter in the Active sheet to point to the range specified\.
**Note: You will normally want to use [SetAutoFilter\(Integer, Integer, Integer\)](SetAutoFilter.md#texcelfilesetautofilterinteger-integer-integer),** since that is the common way to set autofilters\. The last row shouldn't matter, so it will addapt automatically when you add rows\.
If you specify the last row, then the range will still grow to include all data, but it will include at least the last row you specify, even if it is blank\."/>

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetAutoFilter(const row1: Integer; const col1: Integer; const row2: Integer; const col2: Integer); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|Row where the AutoFilter will be placed \(1 based\)\.|
|const|**col1**|Integer|First column for the AutoFilter range \(1 based\)\.|
|const|**row2**|Integer|Last row for the autofilter \(1 based\)\.|
|const|**col2**|Integer|Last column for the AutoFilter range \(1 based\)\. Note that the autofilter will automatically expand over this row if you have more non\-empty rows below this row\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


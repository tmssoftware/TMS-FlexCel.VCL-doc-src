---
uid: TXlsNamedRange.GetRanges
description: TXlsNamedRange.GetRanges
---

# TXlsNamedRange\.GetRanges Method

## Overloads

* [TXlsNamedRange\.GetRanges\(TCoreExcelFile\)](#txlsnamedrangegetrangestcoreexcelfile)
* [TXlsNamedRange\.GetRanges\(TCoreExcelFile, Integer\)](#txlsnamedrangegetrangestcoreexcelfile-integer)

# TXlsNamedRange\.GetRanges\(TCoreExcelFile\)
Returns a list of ranges and cells included in this name\. This can be used to parse for example the PRINT\_TITLES range, which might be something like "1:1,A:A"\. \("," is the union operator in Excel formulas\)\.This method would return an array with the ranges 1:1 and A:A\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.GetRanges(const Workbook: TCoreExcelFile): <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|TCoreExcelFile|File which contains this range\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)

# TXlsNamedRange\.GetRanges\(TCoreExcelFile, Integer\)
Returns a list of ranges and cells included in this name\. This can be used to parse for example the PRINT\_TITLES range, which might be something like "1:1,A:A"\. \("," is the union operator in Excel formulas\)\.This method would return an array with the ranges 1:1 and A:A\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsNamedRange/index.md">TXlsNamedRange</a>.GetRanges(const Workbook: TCoreExcelFile; const targetSheet: Integer): <a href="../TXlsCellRange/index.md">TArray&lt;TXlsCellRange></a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|TCoreExcelFile|File which contains this range\.|
|const|**targetSheet**|Integer|Sheet to target \(1\-based\)\.<br />If any of the ranges does not refer to targetSheet, this method will return null\.<br />To ignore targetSheet and return all ranges, set targetSheet to 0 or to a negative value\.|


## See also

* [TXlsNamedRange](../TXlsNamedRange/index.md)


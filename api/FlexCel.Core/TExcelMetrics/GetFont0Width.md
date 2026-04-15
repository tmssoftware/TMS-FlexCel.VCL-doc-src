---
uid: TExcelMetrics.GetFont0Width
description: TExcelMetrics.GetFont0Width
---

# TExcelMetrics\.GetFont0Width Method

## Overloads

* [TExcelMetrics\.GetFont0Width\(IRowColSize\)](#texcelmetricsgetfont0widthirowcolsize)
* [TExcelMetrics\.GetFont0Width\(IRowColSize, Boolean\)](#texcelmetricsgetfont0widthirowcolsize-boolean)

# TExcelMetrics\.GetFont0Width\(IRowColSize\)
Returns the width of the 0 font on Excel\. Normally this is 7, but can change depending on the file\. The user might modify it by changing Format\->Style\->Normal\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelMetrics/index.md">TExcelMetrics</a>.GetFont0Width(const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>): Double; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)||


## See also

* [TExcelMetrics](../TExcelMetrics/index.md)

# TExcelMetrics\.GetFont0Width\(IRowColSize, Boolean\)
Returns the width of the 0 font on Excel, taking in account the screen dpi, which you set in XlsFile\.ScreenScaling\.
Note that with a scaling more than 100%%, the fontsize returned will be proportionally larger\. So a font that returns 10 points at 100%% will return 20 points at 200%%\. While it makes no sense \(a point is 1/72 of an inch no matter the resolution\) this is the way Excel handles it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TExcelMetrics/index.md">TExcelMetrics</a>.GetFont0Width(const Workbook: <a href="../IRowColSize/index.md">IRowColSize</a>; const UseScreenScaling: Boolean): Double; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Workbook**|[IRowColSize](../IRowColSize/index.md)|File with the font\.|
|const|**UseScreenScaling**|Boolean|If true, we will return the font size at the given screen scaling\. If false, we  will return the font size at 100%% \(96 dpi\)\. Note that if a font is say 7 points at 100%%, it will be 14 points at 200%%\.<br />We need it this way because it is the way Excel uses it\.|


## See also

* [TExcelMetrics](../TExcelMetrics/index.md)


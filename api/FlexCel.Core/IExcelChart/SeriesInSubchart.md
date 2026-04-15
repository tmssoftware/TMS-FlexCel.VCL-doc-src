---
uid: IExcelChart.SeriesInSubchart
description: IExcelChart.SeriesInSubchart
---

# IExcelChart\.SeriesInSubchart Method

Returns the number of series on each subchart\. Note that this property only works in xlsx files: In xls files it will always return 0\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IExcelChart/index.md">IExcelChart</a>.SeriesInSubchart(const subchartPos: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**subchartPos**|Integer|Number of the subchart\. \(1 based\)|


## See also

* [IExcelChart](../IExcelChart/index.md)


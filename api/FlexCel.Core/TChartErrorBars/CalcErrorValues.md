---
uid: TChartErrorBars.CalcErrorValues
description: TChartErrorBars.CalcErrorValues
---

# TChartErrorBars\.CalcErrorValues Method

This method will calculate the Values array based on the error types and series values\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TChartErrorBars/index.md">TChartErrorBars</a>.CalcErrorValues(const NumberOfSeries: Integer; const SeriesLen: Integer; const SeriesVal: TFunc&lt;Integer, Integer, Double&gt;; const SeriesHasVal: TFunc&lt;Integer, Integer, Boolean&gt;; const SeriesPos: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**NumberOfSeries**|Integer|Total number of series\.|
|const|**SeriesLen**|Integer|Length of one series\.|
|const|**SeriesVal**|TFunc\<Integer, Integer, Double>|Function that returns the value of a point of one of the series\. First parameter is the series number, second is the point position\.|
|const|**SeriesHasVal**|TFunc\<Integer, Integer, Boolean>|Function that returns true if a point of the series exists\. First parameter is the series number, second is the point position\.|
|const|**SeriesPos**|Integer|Series for which we are calculating the values\.|


## See also

* [TChartErrorBars](../TChartErrorBars/index.md)


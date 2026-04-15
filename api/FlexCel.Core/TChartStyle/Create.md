---
uid: TChartStyle.Create
description: TChartStyle.Create
---

# TChartStyle\.Create Method

Creates a new chart style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TChartStyle/index.md">TChartStyle</a>.Create(const aStyle: Integer): <a href="../TChartStyle/index.md">TChartStyle</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aStyle**|Integer|Style id\. This number must be between 1 and 48 or 101 and 148\. If it is outside this range, the style id will be initialized to 2\. Numbers between 101 and 148 are extended styles which correspond  to the numbers between 1 and 48, but with the IsExtended flag true\.|


## See also

* [TChartStyle](../TChartStyle/index.md)


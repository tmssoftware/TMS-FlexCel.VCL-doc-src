---
uid: TCustomizeChartEventArgs.Create
description: TCustomizeChartEventArgs.Create
---

# TCustomizeChartEventArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TCustomizeChartEventArgs/index.md">TCustomizeChartEventArgs</a>.Create(const aExcelFile: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const aChart: <a href="../../FlexCel.Core/IExcelChart/index.md">IExcelChart</a>; const aChartName: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExcelFile**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|The ExcelFile that has the chart\.|
|const|**aChart**|[IExcelChart](../../FlexCel.Core/IExcelChart/index.md)|Chart being processed\. You can modify its properties in this event\.|
|const|**aChartName**|string|Name of the chart\.|


## See also

* [TCustomizeChartEventArgs](../TCustomizeChartEventArgs/index.md)


---
uid: TFlexCelReport.PreLoad
description: TFlexCelReport.PreLoad
---

# TFlexCelReport\.PreLoad Method

Used on included reports\. For performance, the report will be parsed only once\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.PreLoad(const aWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; var startingBand: TBand; const sheetToLoad: Integer; var ReportData: TBytes; out KeepRows: TFVList&lt;TKeepTogether&gt;; out KeepCols: TFVList&lt;TKeepTogether&gt;);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)||
|var|**startingBand**|TBand||
|const|**sheetToLoad**|Integer||
|var|**ReportData**|TBytes||
|out|**KeepRows**|TFVList\<TKeepTogether>||
|out|**KeepCols**|TFVList\<TKeepTogether>||


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


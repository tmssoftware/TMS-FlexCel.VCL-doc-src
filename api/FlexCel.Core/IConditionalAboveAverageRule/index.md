---
uid: IConditionalAboveAverageRule
description: IConditionalAboveAverageRule
---

# IConditionalAboveAverageRule Interface

A conditional format rule which highlights cells which are below or above the average value of the group of cells\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">IConditionalAboveAverageRule = interface(<a href="../IConditionalFormatStandardDefRule/index.md">IConditionalFormatStandardDefRule</a>);</code></pre>

## Properties

|Name|Description|
|---|---|
|[IsBelowAverage](IsBelowAverage.md)|If true, then this rule highlights values below the average instead of above\.<br />|
|[IncludeAverage](IncludeAverage.md)|If true, the average value itself will be highlighted\.<br />|
|[StdDev](StdDev.md)|The number of standard deviations to include above or below the average\.<br />|



---
uid: TFlxNumberFormat.PercentCount
description: TFlxNumberFormat.PercentCount
---

# TFlxNumberFormat\.PercentCount Method

Returns the number of %% sign in a cell\. Each %% in the format string multiplies the value by 100, so 0\.1 formatted as "0%%" will display as 10%% and formatted as 0%%%% will display as 1000%%%%\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxNumberFormat/index.md">TFlxNumberFormat</a>.PercentCount(const Value: <a href="../TCellValue/index.md">TCellValue</a>; const Format: string): Integer; static;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Value**|[TCellValue](../TCellValue/index.md)|Value we are formatting\. Normally this shouldn't affect the number of percents in the format string, but if the format string is different for positive and negative numbers or zero values, then the value might affect the result\.|
|const|**Format**|string|Cell format\.|


## See also

* [TFlxNumberFormat](../TFlxNumberFormat/index.md)


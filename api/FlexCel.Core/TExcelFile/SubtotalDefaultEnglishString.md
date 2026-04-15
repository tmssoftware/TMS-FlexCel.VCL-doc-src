---
uid: TExcelFile.SubtotalDefaultEnglishString
description: TExcelFile.SubtotalDefaultEnglishString
---

# TExcelFile\.SubtotalDefaultEnglishString Method

Returns the english string that Excel uses to refer to Sums, averages, et\. when you use the Subtotal command\. You can use the result of this method together with [Subtotal](Subtotal.md) to specify the text for totals\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.SubtotalDefaultEnglishString(const aggFunction: Integer): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aggFunction**|Integer|Number of function used for aggregating\. If the number is unknown then this function will return "Total"\.<br />For known numbers this function will return what Excel writes on the cells for that function\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


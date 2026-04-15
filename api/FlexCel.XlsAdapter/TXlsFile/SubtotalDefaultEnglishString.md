---
uid: TXlsFile.SubtotalDefaultEnglishString
description: TXlsFile.SubtotalDefaultEnglishString
---

# TXlsFile\.SubtotalDefaultEnglishString Method

Returns the english string that Excel uses to refer to Sums, averages, et\. when you use the Subtotal command\. You can use the result of this method together with [TExcelFile.Subtotal](../../FlexCel.Core/TExcelFile/Subtotal.md) to specify the text for totals\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.SubtotalDefaultEnglishString(const aggFunction: Integer): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aggFunction**|Integer|Number of function used for aggregating\. If the number is unknown then this function will return "Total"\.<br />For known numbers this function will return what Excel writes on the cells for that function\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


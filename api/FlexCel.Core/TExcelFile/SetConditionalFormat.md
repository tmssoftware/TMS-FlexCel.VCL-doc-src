---
uid: TExcelFile.SetConditionalFormat
description: TExcelFile.SetConditionalFormat
---

# TExcelFile\.SetConditionalFormat Method

Modifies one of the conditional format rules in the sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetConditionalFormat(const index: Integer; const formatCondition: <a href="../TConditionalFormat/index.md">TConditionalFormat</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the conditional format to modify\. 1\-based\.|
|const|**formatCondition**|[TConditionalFormat](../TConditionalFormat/index.md)|The conditional format rules to apply to a set of ranges in the active sheet\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


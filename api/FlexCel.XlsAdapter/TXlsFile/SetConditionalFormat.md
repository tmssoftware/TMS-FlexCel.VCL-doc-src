---
uid: TXlsFile.SetConditionalFormat
description: TXlsFile.SetConditionalFormat
---

# TXlsFile\.SetConditionalFormat Method

Modifies one of the conditional format rules in the sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetConditionalFormat(const index: Integer; const formatCondition: <a href="../../FlexCel.Core/TConditionalFormat/index.md">TConditionalFormat</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the conditional format to modify\. 1\-based\.|
|const|**formatCondition**|[TConditionalFormat](../../FlexCel.Core/TConditionalFormat/index.md)|The conditional format rules to apply to a set of ranges in the active sheet\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.Recalc
description: TXlsFile.Recalc
---

# TXlsFile\.Recalc Method

When [TExcelFile.RecalcMode](../../FlexCel.Core/TExcelFile/RecalcMode.md) is manual, use this method to force a recalculation of the spreadsheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Recalc(const forced: Boolean); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**forced**|Boolean|When true this method will always perform a recalc\. When false, only if there has been a change on the spreadsheet\.<br />While for performance reasons you will normally want to keep this false, you might need to set it to true if the formulas refer to functions like "=NOW\(\)" or "=RANDOM\(\)" that change every time you recalculate\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


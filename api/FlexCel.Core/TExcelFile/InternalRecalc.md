---
uid: TExcelFile.InternalRecalc
description: TExcelFile.InternalRecalc
---

# TExcelFile\.InternalRecalc Method

Used by the framework to recalculate linked spreadsheets\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.InternalRecalc(const forced: Boolean; const Ufl: <a href="../TUnsupportedFormulaList/index.md">TUnsupportedFormulaList</a>; const aCalcLoop: TDropoutStack&lt;<a href="../TCellAddressWithFileName/index.md">TCellAddressWithFileName</a>&gt;); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**forced**|Boolean||
|const|**Ufl**|[TUnsupported&#8203;Formula&#8203;List](../TUnsupportedFormulaList/index.md)||
|const|**aCalcLoop**|TDropoutStack\<[TCellAddress&#8203;With&#8203;File&#8203;Name](../TCellAddressWithFileName/index.md)>||


## See also

* [TExcelFile](../TExcelFile/index.md)


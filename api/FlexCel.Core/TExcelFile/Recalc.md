---
uid: TExcelFile.Recalc
description: TExcelFile.Recalc
---

# TExcelFile\.Recalc Method

## Overloads

* [TExcelFile\.Recalc](#texcelfilerecalc)
* [TExcelFile\.Recalc\(Boolean\)](#texcelfilerecalcboolean)

# TExcelFile\.Recalc
When [RecalcMode](RecalcMode.md) is manual, use this method to force a recalculation of the spreadsheet\.
This specific version of the method will always perform a recalc, even if it is not needed\.
You can use [Recalc\(Boolean\)](Recalc.md#texcelfilerecalcboolean) to recalc only when is needed\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Recalc; overload;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.Recalc\(Boolean\)
When [RecalcMode](RecalcMode.md) is manual, use this method to force a recalculation of the spreadsheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.Recalc(const forced: Boolean); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**forced**|Boolean|When true this method will always perform a recalc\. When false, only if there has been a change on the spreadsheet\.<br />While for performance reasons you will normally want to keep this false, you might need to set it to true if the formulas refer to functions like "=NOW\(\)" or "=RANDOM\(\)" that change every time you recalculate\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


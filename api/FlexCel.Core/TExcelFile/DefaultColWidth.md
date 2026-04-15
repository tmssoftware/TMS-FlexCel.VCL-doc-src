---
uid: TExcelFile.DefaultColWidth
description: TExcelFile.DefaultColWidth
---

# TExcelFile.DefaultColWidth Property

The default width for empty columns, in Excel internal units\. \(Character width of font 0 / 256\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TExcelMetrics.ColMult](../TExcelMetrics/ColMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.DefaultColWidth: Integer</code></pre>

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColWidthInPixels := xls.GetColWidth(Col) / TExcelMetrics.ColMult(xls);</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


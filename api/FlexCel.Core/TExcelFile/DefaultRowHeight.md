---
uid: TExcelFile.DefaultRowHeight
description: TExcelFile.DefaultRowHeight
---

# TExcelFile.DefaultRowHeight Property

The default height for empty rows, in Excel internal units\. \(1/20th of a point\)\. **IMPORTANT:** For this property to have any effect, you also need to set [DefaultRowHeightAutomatic](DefaultRowHeightAutomatic.md) = false\.
To get the real default row height Excel will use when [DefaultRowHeightAutomatic](DefaultRowHeightAutomatic.md) = true or [DefaultRowHidden](DefaultRowHidden.md) = true use [DefaultRowHeightVisual](DefaultRowHeightVisual.md)  See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.DefaultRowHeight: Integer</code></pre>

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


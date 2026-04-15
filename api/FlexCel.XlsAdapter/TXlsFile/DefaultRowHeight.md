---
uid: TXlsFile.DefaultRowHeight
description: TXlsFile.DefaultRowHeight
---

# TXlsFile.DefaultRowHeight Property

The default height for empty rows, in Excel internal units\. \(1/20th of a point\)\. **IMPORTANT:** For this property to have any effect, you also need to set [TExcelFile.DefaultRowHeightAutomatic](../../FlexCel.Core/TExcelFile/DefaultRowHeightAutomatic.md) = false\.
To get the real default row height Excel will use when [TExcelFile.DefaultRowHeightAutomatic](../../FlexCel.Core/TExcelFile/DefaultRowHeightAutomatic.md) = true or [TExcelFile.DefaultRowHidden](../../FlexCel.Core/TExcelFile/DefaultRowHidden.md) = true use [TExcelFile.DefaultRowHeightVisual](../../FlexCel.Core/TExcelFile/DefaultRowHeightVisual.md)  See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../../FlexCel.Core/TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.DefaultRowHeight: Integer</code></pre>

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


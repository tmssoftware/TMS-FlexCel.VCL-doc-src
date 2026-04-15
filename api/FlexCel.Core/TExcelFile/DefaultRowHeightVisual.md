---
uid: TExcelFile.DefaultRowHeightVisual
description: TExcelFile.DefaultRowHeightVisual
---

# TExcelFile\.DefaultRowHeightVisual Method

The default height for empty rows, in Excel internal units\. \(1/20th of a point\)\. Different from [DefaultRowHeight](DefaultRowHeight.md) this property returns the actual row height as Excel will show it, considering [DefaultRowHidden](DefaultRowHidden.md) and [DefaultRowHeightAutomatic](DefaultRowHeightAutomatic.md)\.
See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.DefaultRowHeightVisual(const useDefaultRowHeightAutomatic: Boolean): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**useDefaultRowHeightAutomatic**|Boolean|If false, the property [DefaultRowHeightAutomatic](DefaultRowHeightAutomatic.md) will be ignored and considered false\.<br />In many cases you will prefer to use the default row height stored in the file, even if DefaultRowHeightAutomatic is true\.|


## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


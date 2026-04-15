---
uid: TExcelFile.SetRowHeight
description: TExcelFile.SetRowHeight
---

# TExcelFile\.SetRowHeight Method

Sets the current Row height, in Excel internal units\. \(1/20th of a point\) See [Excel Internal Units](xref:ExcelInternalUnits) for more information in Excel internal units\.


## Remarks

Use [TFlxConsts.RowMult](../TFlxConsts/RowMult.md) to convert the internal units to pixels\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetRowHeight(const row: Integer; const height: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row Index \(1 based\)|
|const|**height**|Integer|Row height, in Excel internal units\. \(1/20th of a point\)\. See [TFlxConsts.RowMult](../TFlxConsts/RowMult.md)|


## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


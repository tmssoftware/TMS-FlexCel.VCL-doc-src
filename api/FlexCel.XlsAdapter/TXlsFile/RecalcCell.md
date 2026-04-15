---
uid: TXlsFile.RecalcCell
description: TXlsFile.RecalcCell
---

# TXlsFile\.RecalcCell Method

This method will recalculate a single cell and all of it's dependencies, but not the whole workbook\.
**USE THIS METHOD WITH CARE\!** You will normally want to simply call [TExcelFile.Recalc](../../FlexCel.Core/TExcelFile/Recalc.md) or just save the file and let FlexCel calculate the workbook for you\.
This method is for rare situations where you are making thousands of recalculations and the speed of Recalc is not enough,  and you have a big part of the spreadsheet that you know that didn't change\.

**Note:** If you are recalculating many cells without changing data, you can speed up calculations by calling [TExcelFile.StartBatchRecalcCells](../../FlexCel.Core/TExcelFile/StartBatchRecalcCells.md) and [TExcelFile.EndBatchRecalcCells](../../FlexCel.Core/TExcelFile/EndBatchRecalcCells.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.RecalcCell(const sheet: Integer; const row: Integer; const col: Integer; const forced: Boolean): <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet for the cell we want to recalculate\. Use [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) here to refer to the active sheet\.|
|const|**row**|Integer|Row for the cell we want to recalculate\. \(1 based\)|
|const|**col**|Integer|Column for the cell we want to recalculate\. \(1 based\)|
|const|**forced**|Boolean|When true this method will always perform a recalc\. When false, only if there has been a change on the spreadsheet\.<br />While for performance reasons you will normally want to keep this false, you might need to set it to true if the formulas refer to functions like "=NOW\(\)" or "=RANDOM\(\)" that change every time you recalculate\.|


## Returns

The result of the formula at the cell, or null if there is no formula\.

## Examples

The following code will recalculate the value of cells A1 and A2, but not C7:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultValue: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=A2 + 5'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=A3 * 2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">7</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">7</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=A3 * 2'</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultValue := xls.RecalcCell(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  Assert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(ResultValue.AsNumber = </span><span style="color:#098658;--shiki-dark:#B5CEA8">19</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'RecalcCell returns the value at the cell.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  Assert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(xls.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult = </span><span style="color:#098658;--shiki-dark:#B5CEA8">19</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Cell A1 was recalculated because we called RecalcCell on it.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  Assert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(xls.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult = </span><span style="color:#098658;--shiki-dark:#B5CEA8">14</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Cell A2 was recalculated because A1 depends on A2.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  Assert</span><span style="color:#000000;--shiki-dark:#D4D4D4">(xls.GetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">7</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">).AsFormula.FormulaResult = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Cell C7 was NOT recalculated because A1 doesn''t have a dependency with it. Call xlsFile.Recalc() to recalc all cells.'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


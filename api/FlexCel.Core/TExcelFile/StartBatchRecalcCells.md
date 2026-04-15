---
uid: TExcelFile.StartBatchRecalcCells
description: TExcelFile.StartBatchRecalcCells
---

# TExcelFile\.StartBatchRecalcCells Method

This method tells FlexCel that you are going to call multiple times [RecalcCell](RecalcCell.md) without changing any data in the spreadsheet\. This way, FlexCel won't keep recalculating the same supporting cells each time you call RecalcCells\.


Always match this call with a call to [EndBatchRecalcCells](EndBatchRecalcCells.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.StartBatchRecalcCells; virtual; abstract;</code></pre>

## Examples

Let's imagine that you want to read the values of cell A1 and cell A2 in a spreadsheet\. Let's also imagine that both A1 and A2 depend on cell B1 and B1 depends in a lot of other cells\. If you call [RecalcCell](RecalcCell.md) first in A1 and then in A2, FlexCel will recalculate B1 and all the cells B1 depends on twice\. But if you wrap both calls in Start/EndBatchRecalcCells:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  A1Value: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  A2Value: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Tell FlexCel that from here, all calls to RecalcCell can use the values calculated by previous calls</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //to RecalcCells.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.StartBatchRecalcCells;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  A1Value := xls.RecalcCell(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  A2Value := xls.RecalcCell(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//This will not recalculate again anything the previous call calculated.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   //Go back to normal mode.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.EndBatchRecalcCells;</span></span>
<span class="line"></span></code></pre>


Then FlexCel will calculate B1 only when calculating A1, and will not calculate it again when calculating A2\.


## See also

* [TExcelFile](../TExcelFile/index.md)


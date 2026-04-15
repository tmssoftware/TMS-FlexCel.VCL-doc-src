---
uid: TExcelFile.RecalcVersion
description: TExcelFile.RecalcVersion
---

# TExcelFile.RecalcVersion Property

Defines which version of Excel recalculation engine will be saved in the file\. This affects how Excel will recalculate the file on open\.


If you set this property for example to Excel2007, then any Excel version newer than Excel 2007  will recalculate all formulas when you load the file, so it will modify the workbook and will ask for saving changes when closing\. Even if you just open and close the file\.
Note that this will only happen if there are formulas on the sheet\.


**If there are any formulas that FlexCel can't recalculate, you should set this property to AlwaysRecalc\.** For example, if you have the formula:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>"=GETPIVOTDATA("a";"b")"</span></span>
<span class="line"><span></span></span></code></pre>

FlexCel will return \#NAME?, as it doesn't implement this function\. If you open this file on Excel and  RecalcVersion was not AlwaysRecalc when saving, Excel will not calculate it and will show also \#NAME?\.
If RecalcVersion was AlwaysRecalc, Excel will show the right answer, but will ask for saving the file when closing\.




## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcVersion: <a href="../TRecalcVersion.md">TRecalcVersion</a></code></pre>

## Examples

The following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//We can't change the recalcmode once we have opened or created the file.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.RecalcMode := TRecalcMode.Manual;  </span><span style="color:#008000;--shiki-dark:#6A9955">//So the sheet is not recalculated before saving.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.NewFile(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2021);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create the file *after* recalcmode was changed.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.RecalcVersion := TRecalcVersion.Excel2021;  </span><span style="color:#008000;--shiki-dark:#6A9955">//So Excel equal or older than 2021 won't recalculate either.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.SetCellValue(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TFormula.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'= 1 + 1'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">));  </span><span style="color:#008000;--shiki-dark:#6A9955">//Basic math...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(OutFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

will create a file with a formula "1 \+ 1" and result = 3 on cell A1\. If RecalcVersion was TRecalcVersion\.AlwaysRecalc, Excel would show the correct value when opening\.


## See also

* [TExcelFile](../TExcelFile/index.md)


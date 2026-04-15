---
uid: TXlsFile.DeleteNamedRange
description: TXlsFile.DeleteNamedRange
---

# TXlsFile\.DeleteNamedRange Method

Deletes the name at the specified position\. **Important:** If the name you are trying to delete is referenced by any formula/chart/whatever in your file, the name will **not actually be deleted** but hidden\.

You won't see the name in Excel or in the formula, but it will be there and you can see it from FlexCel\.
You can use [TExcelFile.GetUsedNamedRanges](../../FlexCel.Core/TExcelFile/GetUsedNamedRanges.md) to learn if a range might be deleted\.
*Also, note that if you later delete the formulas that reference those ranges FlexCel will remove those hanging ranges when saving\.* The only hidden ranges that will be present in the final file will be those that have active formulas referencing them\.


**Important:**If the name wasn't deleted, [TExcelFile.NamedRangeCount](../../FlexCel.Core/TExcelFile/NamedRangeCount.md) will not change\. This means that you can't have code like this:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  while</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.NamedRangeCount > </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span><span style="color:#008000;--shiki-dark:#6A9955">  //WRONG! This loop might never end.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.DeleteNamedRange(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Might not be deleted, and NamedRangeCount will never be 0.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>


The correct code in this case would be:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := xls.NamedRangeCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">downto</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.DeleteNamedRange(i);</span></span>
<span class="line"></span></code></pre>



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteNamedRange(const index: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**index**|Integer|Index of the name to delete \(1 based\)\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


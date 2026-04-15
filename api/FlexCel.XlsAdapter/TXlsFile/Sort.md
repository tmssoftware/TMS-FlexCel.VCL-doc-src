---
uid: TXlsFile.Sort
description: TXlsFile.Sort
---

# TXlsFile\.Sort Method

Sorts a range on the current sheet\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Sort(const Range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const ByRows: Boolean; const Keys: TArray&lt;Int32>; const SortOrder: <a href="../../FlexCel.Core/TSortOrder.md">TArray&lt;TSortOrder></a>; const Comparer: TComparer&lt;<a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>&gt;; const SortFormulaMode: <a href="../../FlexCel.Core/TSortFormulaMode.md">TSortFormulaMode</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range to sort\. It must not include headers\.|
|const|**ByRows**|Boolean|If true, rows will be sorted\. If false, columns will\.|
|const|**Keys**|TArray\<Int32>|An array of integers indicating the columns or rows you want to use for sorting\. Note that this number is absolute, for example column 1 always means column "A" no matter if the range we are sorting begins at column "B"\.<br />A null array means sort by the first column or row, then by the second, etc\. up to 8 entries\.|
|const|**SortOrder**|[TArray\<TSortOrder>](../../FlexCel.Core/TSortOrder.md)|An array of flags indicating whether to sort ascending or descending for each Key\. If null, all sorts will be ascending\. If not null and the array size is less than the size of the "Keys" parameter, all missing entries are assumed to be Ascending\.|
|const|**Comparer**|TComparer\<[TCellValue](../../FlexCel.Core/TCellValue/index.md)>|Comparer to create a custom way to compare the different items\. Set it to null to use default ordering\.|
|const|**SortFormulaMode**|[TSortFormulaMode](../../FlexCel.Core/TSortFormulaMode.md)|Defines how formulas in the file will be changed when sorting\.|


## Examples

To sort the range of cells from B7 to D100, on columns B Ascending and C Descending using [TSortFormulaMode.ExcelLike](../../FlexCel.Core/TSortFormulaMode.md):

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Sort(</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TXlsCellRange.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'B7:D100'</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#008000;--shiki-dark:#6A9955">//To sort the full sheet, you can pass TXlsCellRange.Null here.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">//Normally we want to sort the rows in the range. But we might want to sort columns and we can do it by setting this to false.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Int32Array.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#008000;--shiki-dark:#6A9955">// Sort by columns B and C (2 and 3)</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TArray&#x3C;TSortOrder>.Create(TSortOrder.Ascending, TSortOrder.Descending), </span><span style="color:#008000;--shiki-dark:#6A9955">//Sort column B ascending, column C descending. If you want to sort everything in ascending order, just set this to nil.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#008000;--shiki-dark:#6A9955">// Use the standard comparer.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    TSortFormulaMode.ExcelLike </span><span style="color:#008000;--shiki-dark:#6A9955">//Excel-like is faster, but won't change formulas outside the range being sorted.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  );</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


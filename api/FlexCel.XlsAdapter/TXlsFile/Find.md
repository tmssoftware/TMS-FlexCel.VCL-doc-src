---
uid: TXlsFile.Find
description: TXlsFile.Find
---

# TXlsFile\.Find Method

Finds a value inside a cell and returns the position for the cell, or null if nothing was found\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.Find(const value: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const Range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const Start: <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; const ByRows: Boolean; const CaseInsensitive: Boolean; const SearchInFormulas: Boolean; const WholeCellContents: Boolean): <a href="../../FlexCel.Core/TCellAddress/index.md">TCellAddress</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**value**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Value we are searching\.|
|const|**Range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range to Search\. Null means the whole worksheet\.|
|const|**Start**|[TCellAddress](../../FlexCel.Core/TCellAddress/index.md)|Cell where to start searching\. For the first time, use null\. After this, you can use the result of this method to get the next cell\.|
|const|**ByRows**|Boolean|If true, the value will be searched down then left\. If false, the search will go left then down\. SEARCH IS FASTER WHEN BYROWS = FALSE|
|const|**CaseInsensitive**|Boolean|If true, string searches will not be case sensitive, "a" = "A"|
|const|**SearchInFormulas**|Boolean|If true, the search will cover formulas too\.|
|const|**WholeCellContents**|Boolean|If true, the string must match the whole cell, not a part of it\.|


## Returns

Cell where the string is found, or null if it is not found\.

## Examples

To find all cells on a sheet that contain the string "bolts":

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Cell: TCellAddress;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  Cell := TCellAddress.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Empty</span><span style="color:#000000;--shiki-dark:#D4D4D4">;  </span><span style="color:#008000;--shiki-dark:#6A9955">//initialize the value to null to start searching.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  repeat</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    Cell := xls.Find(</span><span style="color:#A31515;--shiki-dark:#CE9178">'bolts'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TXlsCellRange.Null, Cell, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">);  </span><span style="color:#008000;--shiki-dark:#6A9955">//find the next value.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Cell.HasValue </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      LogMessage(Cell.CellRef);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  until</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Cell.IsNull; </span><span style="color:#008000;--shiki-dark:#6A9955">//until it doesn't find any more matches.</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


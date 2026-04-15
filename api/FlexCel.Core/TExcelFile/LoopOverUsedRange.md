---
uid: TExcelFile.LoopOverUsedRange
description: TExcelFile.LoopOverUsedRange
---

# TExcelFile\.LoopOverUsedRange Method

This method loops over a range of cells, and calls an action for every cell that has data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.LoopOverUsedRange(const aRange: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const reader: TProc&lt;<a href="../TLoopOverUsedRangeParameters/index.md">TLoopOverUsedRangeParameters</a>&gt;);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRange**|[TXlsCellRange](../TXlsCellRange/index.md)|Range where we want to extract the cell values\.|
|const|**reader**|TProc\<[TLoopOverUsed&#8203;Range&#8203;Parameters](../TLoopOverUsedRangeParameters/index.md)>|Anonymous method that will be called once for each cell with a value inside the range\.|


## Examples

To fill an array with all the cells in a range, you could use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> GetRangeAsArray</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls: TExcelFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> range: TXlsCellRange): TCellValueArray2;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //We can't capture Result in an anonymous method.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  //So we will use a temporary ResultArray variable.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultArray: TCellValueArray2;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ResultArray := </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  SetLength(ResultArray, range.RowCount, range.ColCount);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.LoopOverUsedRange(range, </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    procedure (x: TLoopOverUsedRangeParameters)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      ResultArray[x.Row - range.Top, x.Col - range.Left] := x.Value;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  exit</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (ResultArray);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)
* [ColCountInRow\(Integer\)](ColCountInRow.md#texcelfilecolcountinrowinteger)
* [ColFromIndex\(Integer, Integer\)](ColFromIndex.md#texcelfilecolfromindexinteger-integer)
* [ColToIndex\(Integer, Integer\)](ColToIndex.md#texcelfilecoltoindexinteger-integer)


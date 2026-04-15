---
uid: TXlsFile.ColToIndex
description: TXlsFile.ColToIndex
---

# TXlsFile\.ColToIndex Method

## Overloads

* [TXlsFile\.ColToIndex\(Integer, Integer\)](#txlsfilecoltoindexinteger-integer)
* [TXlsFile\.ColToIndex\(Integer, Integer, Integer\)](#txlsfilecoltoindexinteger-integer-integer)

# TXlsFile\.ColToIndex\(Integer, Integer\)
This is the inverse of [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer)\. It will return the index on the  internal column array from the row for an existing column\. If the column doesn't exist, it will return the  index of the "LAST existing column less than col", plus 1\.
You can use this together with [TExcelFile.ColCountInRow\(Integer\)](../../FlexCel.Core/TExcelFile/ColCountInRow.md#texcelfilecolcountinrowinteger) and [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer) to iterate faster on a block\.
Or you can call [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md) for a method that does the looping for you using those methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ColToIndex(const row: Integer; const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer|Row \(1 based\)|
|const|**col**|Integer|Column \(1 based\)|


## Returns

The index on the column list for the row\. \(1 based\)

## Examples

To loop on all the existing cells range you can use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastCIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastUsedRow: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // Loop at most until the last used row in the sheet.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // If LastRow is for example 1.000.000, but there are only</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // 3 used rows, it makes no sense to loop over all the empty rows after row 3.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastUsedRow := Math.Min(LastRow, xls.RowCount);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  </span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row := FirstRow </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastUsedRow </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LastCIndex := xls.ColToIndex(row, LastColumn);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LastColFromIndex := xls.ColFromIndex(row, LastCIndex);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (LastColFromIndex > LastColumn) or (LastColFromIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#008000;--shiki-dark:#6A9955">  // LastColumn does not exist.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Dec(LastCIndex);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastCIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#008000;--shiki-dark:#6A9955">  // This row is empty. Move to the next row.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      continue</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    XF := -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cIndex := xls.ColToIndex(row, FirstColumn) </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastCIndex </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      DoSomething(row, xls.ColFromIndex(row, cIndex), xls.GetCellValueIndexed(row, cIndex, XF));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

Note that this example is the implementation of [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md), so you might want to directly call [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md) instead of pasting this example in your code\.


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.ColCountInRow\(Integer\)](../../FlexCel.Core/TExcelFile/ColCountInRow.md#texcelfilecolcountinrowinteger)
* [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer)
* [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md)

# TXlsFile\.ColToIndex\(Integer, Integer, Integer\)
This is the inverse of [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer)\. It will return the index on the  internal column array from the row for an existing column\. If the column doesn't exist, it will return the  index of the "LAST existing column less than col", plus 1\.
You can use this together with [TExcelFile.ColCountInRow\(Integer\)](../../FlexCel.Core/TExcelFile/ColCountInRow.md#texcelfilecolcountinrowinteger) and [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer) to iterate faster on a block\.
Or you can call [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md) for a method that does the looping for you using those methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.ColToIndex(const sheet: Integer; const row: Integer; const col: Integer): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheet**|Integer|Sheet where we are working\. It might be different from ActiveSheet\.|
|const|**row**|Integer|Row \(1 based\)|
|const|**col**|Integer|Column \(1 based\)|


## Returns

The index on the column list for the row\. \(1 based\)

## Examples

To loop on all the existing cells on a range you can use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastCIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastUsedRow: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // Loop at most until the last used row in the sheet.</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // If LastRow is for example 1.000.000, but there are only</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">  // 3 used rows, it makes no sense to loop over all the empty rows after row 3.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  LastUsedRow := Math.Min(LastRow, xls.RowCount);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  </span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row := FirstRow </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastUsedRow </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LastCIndex := xls.ColToIndex(row, LastColumn);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    LastColFromIndex := xls.ColFromIndex(row, LastCIndex);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> (LastColFromIndex > LastColumn) or (LastColFromIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">) </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#008000;--shiki-dark:#6A9955">  // LastColumn does not exist.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      Dec(LastCIndex);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastCIndex = </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span><span style="color:#008000;--shiki-dark:#6A9955">  // This row is empty. Move to the next row.</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      continue</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    XF := -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cIndex := xls.ColToIndex(row, FirstColumn) </span><span style="color:#0000FF;--shiki-dark:#569CD6">to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> LastCIndex </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      DoSomething(row, xls.ColFromIndex(row, cIndex), xls.GetCellValueIndexed(row, cIndex, XF));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

Note that this example is the implementation of [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md), so you might want to directly call [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md) instead of pasting this example in your code\.


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.ColCountInRow\(Integer\)](../../FlexCel.Core/TExcelFile/ColCountInRow.md#texcelfilecolcountinrowinteger)
* [TExcelFile.ColFromIndex\(Integer, Integer\)](../../FlexCel.Core/TExcelFile/ColFromIndex.md#texcelfilecolfromindexinteger-integer)
* [TExcelFile.LoopOverUsedRange](../../FlexCel.Core/TExcelFile/LoopOverUsedRange.md)


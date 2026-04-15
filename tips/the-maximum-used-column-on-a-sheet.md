---
uid: TheMaximumUsedColumnOnASheet
---

# The maximum used column on a sheet.

This one looks simple enough. What is the maximum used column on a sheet?  In Excel, you can find out with this macro:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">Sub</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> Macro1</span><span style="color:#000000;--shiki-dark:#D4D4D4">() </span></span>
<span class="line"><span style="color:#795E26;--shiki-dark:#DCDCAA">      Range</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">"a1"</span><span style="color:#000000;--shiki-dark:#D4D4D4">).</span><span style="color:#001080;--shiki-dark:#9CDCFE">FormulaR1C1</span><span style="color:#000000;--shiki-dark:#D4D4D4"> = ActiveSheet.UsedRange.Address </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">End Sub</span></span>
<span class="line"></span></code></pre>

In FlexCel, we have not one, but two methods to get this information:  
 * [TExcelFile.ColCount](~/api/FlexCel.Core/TExcelFile/ColCount.md)
 * [TExcelFile.ColCountOnlyData](~/api/FlexCel.Core/TExcelFile/ColCountOnlyData.md)
And yet, how to get the column count is a common [question in our inbox](https://support.tmssoftware.com/t/colcountdataonly-counts-column-with-formatting-only/12394). The main problem being, everyone has a different definition in mind of what "ColCount" should return.

The first question that comes to mind is: Should we include formatted columns in the result? For example, in the image below, should ColCount return 2 or 5?

<img alt = "colcount with formatted columns" src = "../images/colcount-with-formatted-columns.png" width = "434" height = "170"/>

That's why we have two different methods to measure the column count. [TExcelFile.ColCount](~/api/FlexCel.Core/TExcelFile/ColCount.md) will include formatted columns (column E in the example above), and [TExcelFile.ColCountOnlyData](~/api/FlexCel.Core/TExcelFile/ColCountOnlyData.md) won't.

But this is just the entrance to the rabbit hole. The next question to answer is, "Should we include blank formatted cells in the count?"  And there is no simple answer, as it depends on why you want the column count for.

Let's say we want to calculate the range of visible cells that we want to print and let's imagine we have the following spreadsheet:

<img alt = "colcount with visible formatted cells" src = "../images/colcount-with-visible-formatted-cells.png" width = "435" height = "170"/>

It seems evident that if you want to print that sheet, you should include cell E5. And both ColCount and ColCountOnlyData in FlexCel will include cell E5 because both count blank formatted cells.
But let's imagine now that cell E5 was bold, with a white background. It now makes no sense to include E5, since it won't be visible when you print it. So for printing, neither ColCountOnlyData nor ColCount will work. We would need a "MaxPrintableColumn" method, including an empty cell with a yellow background, but not including an empty cell with bold formatting.

Now let's consider a case like the following:

<img alt = "colcount with span" src = "../images/colcount-with-span.png" width = "367" height = "76"/>

Again, depending on what your need is for the column count, the result changes. If you need to process the cells with data, then the last column with Data is A. But if you need to print the sheet, you should print it up to column D.

And we can keep going for a while. What happens if the last column with data is hidden? It shouldn't count for printing, but it should count for processing data. And what if the cell has a formula, and the formula has an empty result? Should the cell be considered empty?  Should we consider empty a cell that only has whitespace? Or a cell with a formula that returns 0, if the "display zeros" option in the workbook is off? When we start combining all the options, it turns out that we would need a lot of methods or parameters to accommodate them all, and we might still miss the particular combination that looks like the "logical" ColCount output given your situation.

The final issue with all ColCount variants is that no variant would be efficient. Given that FlexCel stores the cells grouped by rows, finding the maximum column means looping over all rows to find the maximum. It is not something that we can do more efficiently than you could. So to sum it up:

  1. For most cases, you shouldn't use ColCount or ColCountOnlyData at all. Use [TExcelFile.ColCountInRow](~/api/FlexCel.Core/TExcelFile/ColCountInRow.md) instead. It is not just that ColCount is slow to compute, it is also that it calculates the maximum enclosing rectangle, and that can include lots of empty cells. See the [Performance Guide](xref:PerformanceGuide#avoid-calling-colcount) for more information.

  2. For the cases where you really need a column count, decide which is the exact column count that you want. Do you need to include empty formatted cells, formatted columns, etc? Then you can use the following code to calculate it: 

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">class</span><span style="color:#0000FF;--shiki-dark:#569CD6"> function</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> DocMaxColCount.CalcMaxColumn</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls: TExcelFile): </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowCount: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MaxCol: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColCountInRow: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  colIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  XF: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cellValue: TCellValue;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  c: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowCount := xls.RowCount;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  MaxCol := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> RowCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    ColCountInRow := xls.ColCountInRow(row);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> colIndex := ColCountInRow </span><span style="color:#AF00DB;--shiki-dark:#C586C0">downto</span><span style="color:#098658;--shiki-dark:#B5CEA8"> 1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      XF := -</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      cellValue := xls.GetCellValueIndexed(row, colIndex, XF);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> cellValue.IsEmpty </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span><span style="color:#008000;--shiki-dark:#6A9955">  // you can add some other condition here like if it is a RichString and the richstring is whitespace</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">        continue</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      c := xls.ColFromIndex(row, colIndex);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> c > MaxCol </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        MaxCol := c;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      break</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := MaxCol;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"></span></code></pre>


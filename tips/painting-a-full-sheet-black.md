# Painting a full sheet black.

Let's imagine we want to paint all cells on a sheet with a black background and a white font. Unfortunately, Excel doesn't have a way to set the format for a full sheet, so that's not an option. 

The first idea is that we could loop over each of the 17 billion cells in the spreadsheet and paint each cell in black. And that would work, but it would not only be very slow (even computers take their time to count to 17 billion), but it would also use a lot of memory. Because we need to create 17 billion empty cells to format them in black. Even when xlsx files are compressed, the file size would be huge, too, as it would be the time it takes for Excel to open the file.

So, no way to set the entire sheet to black, and if we try to format every cell, it won't work either. But there surely is a way, isn't it? If you create a file in Excel, select all cells, and paint them black, the file will not be much bigger than an empty file and will not take vast amounts of memory. Excel somehow manages to do it, and we know it is not setting the format for the entire sheet or for every cell.

Then, how is Excel doing it? As usual, the simplest way to find out is with APIMate. So, let's create an empty file in Excel, paint all the cells black, then save the file and open it with APIMate. And this is the code we get:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColFmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">   ColFmt := xls.GetFormat(xls.GetColFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">));</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColFmt.Font.Color := TExcelColor.FromTheme(TThemeColor.Light1);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColFmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColFmt.FillPattern.FgColor := TExcelColor.FromTheme(TThemeColor.Dark1);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  ColFmt.FillPattern.BgColor := TExcelColor.Automatic;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetColFormat(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">16384</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.AddFormat(ColFmt));</span></span>
<span class="line"></span></code></pre>


While Excel doesn't have a way to format the whole sheet, it has [Cell, Row, and Column formats](xref:ApiDeveloperGuide#cell-formats). A sheet has about 17 billion cells, nearly 1 million rows, and around 16 thousand columns. To format every cell, we would need to set the format in 17 billion cells. To format every row, we would need to set the format in 1 million rows. To format every column, we need to set the format in 16 thousand columns. 

The option requiring fewer formats is formatting every column, which is what Excel does, and what you should do, too, if you want to change the format for a whole sheet.


---
uid: TXlsFile.Subtotal
description: TXlsFile.Subtotal
---

# TXlsFile\.Subtotal Method

This method works like the "Subtotal" command in Excel in the "Data" tab of the ribbon\. It will take a number of cells and group them by similar values, adding a subtotal formula every new different value and a grand total at the end\.
It will also add outlines at the right\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.Subtotal(range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const atChangeInColumn: Integer; const aggFunction: Integer; const subtotalColumns: TArray&lt;Int32>; const SubtotalText: TFunc&lt;Integer, Integer, <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>, string, string&gt;; const grandtotalText: string; const SubTotalRowFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;; const SubTotalCellTextFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;; const SubTotalCellFormulaFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;; const GrandTotalRowFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;; const GrandTotalCellTextFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;; const GrandTotalCellFormulaFormat: TFunc&lt;<a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>, <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>&gt;); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range where to apply the subtotals\. If null, the whole sheet will be used\.|
|const|**atChangeInColumn**|Integer|Index of the column where we want to group in\. Every time a value in this column changes from the previous row, a new subtotal will be added\.|
|const|**aggFunction**|Integer|Function that will be used in the =Subtotal\(\.\.\.\) formula added\. To do a sum, set this value to 9\.<br />For other values, see the Excel reference in the =Subtotal function\.|
|const|**subtotalColumns**|TArray\<Int32>|We will add a subtotal formula in each one of the columns in this array\.|
|const|**SubtotalText**|TFunc\<Integer, Integer, [TCellValue](../../FlexCel.Core/TCellValue/index.md), string, string>|In this function you need to return the text that will be written in every "Subtotal" line\.<br />The parameters to this function are the row, column, and value of the cell we are aggregating, as an object and as a string\. If this function is null, "aggregatedcolumn Total" will be written\.<br />|
|const|**grandtotalText**|string|Text for the grand total line\.<br />If null or empty, no grand total line will be added\. **Note:** You can pass "Grand " \+ the result of [TExcelFile.SubtotalDefaultEnglishString](../../FlexCel.Core/TExcelFile/SubtotalDefaultEnglishString.md) here to get the standard English labels for the function \("Total", "Average", etc\)\.|
|const|**SubTotalRowFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TCellValue](../../FlexCel.Core/TCellValue/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Row format for the subtotal rows added\. You get a TFlxFormat and the cell value for the column you are aggregating, and you must return a changed one with the format you want\. You might leave this function null, and no special format will be applied to the rows\.|
|const|**SubTotalCellTextFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TCellValue](../../FlexCel.Core/TCellValue/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Cell format for the subtotal cells which contain text like "Food Subtotal"\. You get a TFlxFormat and the cell value for the column you are aggregating, and you must return a changed one with the format you want\. You might leave this function null, and **bold** will be applied to all subtotal texts\.|
|const|**SubTotalCellFormulaFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TCellValue](../../FlexCel.Core/TCellValue/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Cell format for the subtotal cells which contain formulas like =Subtotal\(\.\.\.\)\. You get a TFlxFormat and the cell value for the column you are aggregating, and you must return a changed one with the format you want\. You might leave this function null, and no special format will be applied to subtotal formulas\.|
|const|**GrandTotalRowFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Row format for the grand total row added\. You get a TFlxFormat, and you must return a changed one with the format you want\. You might leave this function null, and no special format will be applied to the grand total row\.|
|const|**GrandTotalCellTextFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Cell format for the grand total cells which contain text like "Food Total"\. You get a TFlxFormat, and you must return a changed one with the format you want\. You might leave this function null, and **bold** will be applied to all grand total texts\.|
|const|**GrandTotalCellFormulaFormat**|TFunc\<[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md), [TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)>|Cell format for the grand total cells which contain formulas like =Subtotal\(\.\.\.\)\. You get a TFlxFormat, and you must return a changed one with the format you want\. You might leave this function null, and no special format will be applied to grand total formulas\.|


## Examples

The following example will calculate the Count \(function 3\) of column 2 at every change of column 1\.
It will write "Grand Count" in the big total, and the rest of parameters will be the default\.


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Subtotal(TXlsCellRange.Null, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Int32Array.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Grand '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + xls.SubtotalDefaultEnglishString(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">nil</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>



Below is a more complex example, which will calculate the Average \(function 1\) of columns 4 and 5  at every change of column 3\. This method uses the callbacks to provide custom text for the subtotal lines and custom formats for all possible cases\. This can be useful if default texts aren't enough or you want to use other language than English, but normally most callbacks will be null as the defaults should work in most cases\. This example is just to show all the functionality in a single call\.


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Subtotal(TXlsCellRange.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, xls.RowCount - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, Int32Array.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">5</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">; col: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">; cellVal: TCellValue; cellValAsString: </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span><span style="color:#000000;--shiki-dark:#D4D4D4">): </span><span style="color:#0000FF;--shiki-dark:#569CD6">string</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#A31515;--shiki-dark:#CE9178">'This is the average of '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + cellValAsString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'Super Average'</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat; cellval: TCellValue): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.</span><span style="color:#0000FF;--shiki-dark:#569CD6">Name</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Courier new'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Scheme := TFontScheme.None;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumAquamarine;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat; cellval: TCellValue): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Style := [TFlxFontStyles.Bold];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumBlue;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat; cellval: TCellValue): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Style := [TFlxFontStyles.Italic];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumOrchid;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Style := [TFlxFontStyles.StrikeOut];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumSeaGreen;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Style := [TFlxFontStyles.StrikeOut];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumSpringGreen;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    function (fmt: TFlxFormat): TFlxFormat</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.Font.Style := [TFlxFontStyles.StrikeOut];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fmt.FillPattern.FgColor := Colors.MediumTurquoise;</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">      exit</span><span style="color:#000000;--shiki-dark:#D4D4D4">(fmt);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


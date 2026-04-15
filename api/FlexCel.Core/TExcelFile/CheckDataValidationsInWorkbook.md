---
uid: TExcelFile.CheckDataValidationsInWorkbook
description: TExcelFile.CheckDataValidationsInWorkbook
---

# TExcelFile\.CheckDataValidationsInWorkbook Method

Checks if all the cells in the file inside data validations have values that are valid according to the data validation specifications\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CheckDataValidationsInWorkbook(const maxErrors: Integer): <a href="../TCellAddress/index.md">TArray&lt;TCellAddress></a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**maxErrors**|Integer|The maximum number of errors reported by this method\. To avoid getting a too big list, set it to a number like 100\. If set to 0 or a negative number, the full list of errors will be returned, which can be very big\.|


## Returns

An array with the first maxErrors cells that do not conform to the data validation\. And empty array if all the cells conform\.

## Examples

The following code will mark in red all the cells in a file which don't comply with the data validations and save the file with a different name:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CheckDataValidationsInWorkbook</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> sourceFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> targetFileName: </span><span style="color:#0000FF;--shiki-dark:#569CD6">String</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  cellsWithErrors: TCellAddressArray;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  fmt: TFlxFormat;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xf: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  i: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(sourceFileName, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    cellsWithErrors := xls.CheckDataValidationsInWorkbook(</span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    fmt := xls.GetStyle(xls.GetBuiltInStyleName(TBuiltInStyle.Bad, </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xf := xls.AddFormat(fmt);</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> i := </span><span style="color:#098658;--shiki-dark:#B5CEA8">0</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Length(cellsWithErrors) - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#AF00DB;--shiki-dark:#C586C0"> do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.ActiveSheetByName := cellsWithErrors[i].Sheet;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      xls.SetCellFormat(cellsWithErrors[i].Row, cellsWithErrors[i].Col, xf);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(targetFileName);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


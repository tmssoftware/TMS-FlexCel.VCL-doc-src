---
uid: TExcelFile.RecalcExpression
description: TExcelFile.RecalcExpression
---

# TExcelFile\.RecalcExpression Method

## Overloads

* [TExcelFile\.RecalcExpression\(string\)](#texcelfilerecalcexpressionstring)
* [TExcelFile\.RecalcExpression\(string, Boolean\)](#texcelfilerecalcexpressionstring-boolean)

# TExcelFile\.RecalcExpression\(string\)
Calculates the value of any formula and returns the result\. The expression must be a valid Excel formula, it must start with "=", and cell references that don't specify a sheet \(like for example "=A2"\) will refer to the active sheet\. Cells used by the formula will be recalculated as needed too\.

You can use this method as a simple calculator, or to calculate things like the sum of a range of cells in the spreadsheet\. Look at the example for more information on how to use it\.

Note that we will consider the expression to be located in the cell A1 of the Active sheet\. So for example "=ROW\(\)" will return 1, and "=A2" will return the value of A2 in the active sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcExpression(const expression: string): <a href="../TCellValue/index.md">TCellValue</a>; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**expression**|string|Formula to evaluate\. It must start with "=" and be a valid Excel formula\.|


## Returns

The value of the calculated formula\.

## Examples

To calculate the sum of all the cells in column A of the sheet "Data", you can use the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfile.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.ActiveSheetByName := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Data'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := xls.RecalcExpression(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=Sum(A:A)'</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToNumberInvariant;</span></span>
<span class="line"></span></code></pre>

To calculate a simple expression, you can use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := xls.RecalcExpression(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=1 + 2 * 3'</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToNumberInvariant;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)

# TExcelFile\.RecalcExpression\(string, Boolean\)
Calculates the value of any formula and returns the result\. The expression must be a valid Excel formula, it must start with "=", and cell references that don't specify a sheet \(like for example "=A2"\) will refer to the active sheet\. Cells used by the formula will be recalculated as needed too\.

You can use this method as a simple calculator, or to calculate things like the sum of a range of cells in the spreadsheet\. Look at the example for more information on how to use it\.

Note that we will consider the expression to be located in the cell A1 of the Active sheet\. So for example "=ROW\(\)" will return 1, and "=A2" will return the value of A2 in the active sheet\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.RecalcExpression(const expression: string; const forced: Boolean): <a href="../TCellValue/index.md">TCellValue</a>; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**expression**|string|Formula to evaluate\. It must start with "=" and be a valid Excel formula\.|
|const|**forced**|Boolean|When true this method will always perform a recalc\. When false, only if there has been a change on the spreadsheet\.<br />While for performance reasons you will normally want to keep this false, you might need to set it to true if the formulas refer to functions like "=NOW\(\)" or "=RANDOM\(\)" that change every time you recalculate\.|


## Returns

The value of the calculated formula\.

## Examples

To calculate the sum of all the cells in column A of the sheet "Data", you can use the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'myfile.xls'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.ActiveSheetByName := </span><span style="color:#A31515;--shiki-dark:#CE9178">'Data'</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := xls.RecalcExpression(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=Sum(A:A)'</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToNumberInvariant;</span></span>
<span class="line"></span></code></pre>

To calculate a simple expression, you can use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  Result</span><span style="color:#000000;--shiki-dark:#D4D4D4"> := xls.RecalcExpression(</span><span style="color:#A31515;--shiki-dark:#CE9178">'=1 + 2 * 3'</span><span style="color:#000000;--shiki-dark:#D4D4D4">).ToNumberInvariant;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


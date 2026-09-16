---
uid: TExcelFile.MeasureString
description: TExcelFile.MeasureString
---

# TExcelFile\.MeasureString Method

Returns the size of a TRichString in points\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.MeasureString(const text: <a href="../TRichString/index.md">TRichString</a>; const cellFont: <a href="../TFlxFont/index.md">TFlxFont</a>): <a href="../TUISize/index.md">TUISize</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**text**|[TRichString](../TRichString/index.md)|Rich string to measure\.|
|const|**cellFont**|[TFlxFont](../TFlxFont/index.md)|Font of the cell itself\. This font might change later in the string\.|


## Returns

The size in points

## Examples

To measure the text in cell 1, 1, you can use the code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> MeasureStringExample</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  size: TUISize;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">const</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  row = </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  col = </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'SomeFile.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    size := xls.MeasureString(xls.GetStringFromCell(row, col), xls.GetCellVisibleFormatDef(row, col).Font);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.Replace
description: TXlsFile.Replace
---

# TXlsFile\.Replace Method

Replaces the instances of oldValue by newValue in the active sheet, and allows to specify the cell format and value for every replaced cell\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.Replace(const oldValue: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const newValue: <a href="../../FlexCel.Core/TCellValue/index.md">TCellValue</a>; const Range: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const CaseInsensitive: Boolean; const SearchInFormulas: Boolean; const WholeCellContents: Boolean; const ReplaceAction: TProc&lt;<a href="../../FlexCel.Core/TReplaceAction/index.md">TReplaceAction</a>&gt;): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**oldValue**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Value we want to replace\.|
|const|**newValue**|[TCellValue](../../FlexCel.Core/TCellValue/index.md)|Value we want to use to replace oldValue\.|
|const|**Range**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range to Search\. Null means the whole worksheet\.|
|const|**CaseInsensitive**|Boolean|If true, string searches will not be case sensitive, "a" = "A"|
|const|**SearchInFormulas**|Boolean|If true, the search will cover formulas too\.|
|const|**WholeCellContents**|Boolean|If true, only whole cells will be replaced\.|
|const|**ReplaceAction**|TProc\<[TReplaceAction](../../FlexCel.Core/TReplaceAction/index.md)>|Action to be performed in every replacement\.|


## Returns

The number of replacements done\.

## Examples

To replace all cells on a sheet that contain 1999\-01\-01 with 2003\-01\-01, formatting the cells in column 3 as blue:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.Replace(EncodeDate(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1999</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">), EncodeDate(</span><span style="color:#098658;--shiki-dark:#B5CEA8">2003</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">), TXlsCellRange.Null,</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">,</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    procedure (x: TReplaceAction)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      fm: TFlxFormat;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> x.Col = </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#0000FF;--shiki-dark:#569CD6"> then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        fm := xls.GetFormat(x.XF);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        fm.FillPattern.FgColor := Colors.Red;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        fm.FillPattern.Pattern := TFlxPatternStyle.Solid;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        x.XF := xls.AddFormat(fm);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


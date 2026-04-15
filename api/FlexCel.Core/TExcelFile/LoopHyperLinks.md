---
uid: TExcelFile.LoopHyperLinks
description: TExcelFile.LoopHyperLinks
---

# TExcelFile\.LoopHyperLinks Method

Loops over the list of existing hyperlinks in the active sheet which are at least partially contained in range, and executes action for each one of those links\. This can be faster than looping over all  hyperlinks in a page if you have thousands, since this method uses spatial indexing\.


## Remarks

The list of links that will be returned is frozen at the start of the method\. If you add new links in  the anonymous method "action", this method won't loop over those new links\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.LoopHyperLinks(const range: <a href="../TXlsCellRange/index.md">TXlsCellRange</a>; const fullyInside: Boolean; const action: TProc&lt;<a href="../THyperLink/index.md">THyperLink</a>, <a href="../TXlsCellRange/index.md">TXlsCellRange</a>&gt;); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**range**|[TXlsCellRange](../TXlsCellRange/index.md)|Range of cells for which you want to retrieve the links\.|
|const|**fullyInside**|Boolean|If true, only those links that are fully inside the range will be returned\.<br />If false, links which have only a part inside but also a part outside will be returned too\.|
|const|**action**|TProc\<[THyperLink](../THyperLink/index.md), [TXlsCellRange](../TXlsCellRange/index.md)>|Actions to be applied to every link at least partially included in range\.|


## Examples

The following example will find if there is an hyperlink at cell B3, and if there is some, call DoSomething with the link text\.


<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.LoopHyperLinks(TXlsCellRange.Create(</span><span style="color:#A31515;--shiki-dark:#CE9178">'B3'</span><span style="color:#000000;--shiki-dark:#D4D4D4">), </span><span style="color:#0000FF;--shiki-dark:#569CD6">false</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    procedure (hyperlink: THyperLink; range: TXlsCellRange)</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">      if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> hyperlink.HasValue </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">        DoSomething(hyperlink.Text);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>



Remember that while this method is efficient because the search is indexed, if you want to find for example all links in a column, it is faster to do a single call to LoopHyperLinks\(B1:B10\) than to call LoopHyperLinks\(B1\) to get the link at B1, then LoopHyperLinks\(B2\) for B2 and so on\.


## See also

* [TExcelFile](../TExcelFile/index.md)


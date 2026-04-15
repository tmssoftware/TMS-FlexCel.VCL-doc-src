---
uid: TPrintOptions
description: TPrintOptions
---

# TPrintOptions Enumeration

How the sheet should be printed\. You can mix value together by and'ing and or'ing the flags\.
See the example to see how to set or clear one specific value of the enumeration\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|LeftToRight|0|Print over, then down\. You can change this by using xls\.PrintOverThenDown\.<br />|
|Orientation|1|0= landscape, 1=portrait\. You can change this by using xls\.PrintLandscape\.<br />|
|NoPls|2|if 1, then PaperSize, Scale, Res, VRes, Copies, and Landscape data have not been obtained from the printer, so they are not valid\.<br />MAKE SURE YOU MAKE THIS BIT = 0 \*BEFORE\* CHANGING ANY OTHER OPTION\. THEY WILL NOT CHANGE IF THIS IS NOT SET\.<br />|
|NoColor|3|1= Black and white\. You can change this by using xls\.PrintBlackAndWhite\.<br />|
|Draft|4|1= Draft quality\. You can change this by using xls\.PrintDraftQuality\.<br />|
|Notes|5|1= Print Notes\. Use xls\.PrintComments instead\.<br />|
|NoOrient|6|1=orientation not set|
|UsePage|7|1=use custom starting page number\. Use xls\.PrintFirstPageNumber to set this instead\.<br />|


## Examples

Here we will show how to set the page orientation to landscape or portrait\. You can do this simply by using

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.PrintLandscape := </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>

but if you wanted to do it with PrintOptions, you would do the following:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#008000;--shiki-dark:#6A9955">   // Remember that you can always do xls.PrintLandscape = true instead of this code.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  if</span><span style="color:#000000;--shiki-dark:#D4D4D4"> Landscape </span><span style="color:#0000FF;--shiki-dark:#569CD6">then</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.PrintOptions:= xls.PrintOptions - [TPrintOptions.Orientation, TPrintOptions.NoPls]</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#0000FF;--shiki-dark:#569CD6"> else</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#008000;--shiki-dark:#6A9955">     //ALWAYS REMOVE NOPLS BEFORE CHANGING THE OTHER OPTIONS.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.PrintOptions:= xls.PrintOptions - [TPrintOptions.NoPls];</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.PrintOptions:= xls.PrintOptions + [TPrintOptions.Orientation];</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>





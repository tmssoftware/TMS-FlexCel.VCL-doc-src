---
uid: TXlsFile.AutofitComment
description: TXlsFile.AutofitComment
---

# TXlsFile\.AutofitComment Method

Will return the resized anchor so the size of the comment is enough to fit all the text inside\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.AutofitComment(const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>; const aspectRatio: Double; const dontShrink: Boolean; const adjustment: Double; const adjustmentFixed: Double; const anchor: <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>): <a href="../../FlexCel.Core/TClientAnchor/index.md">TClientAnchor</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text for the comment\.|
|const|**aspectRatio**|Double|If you pass 0 as aspect ratio, FlexCel will only resize the height of the comment, keeping the same width as it already had\. If you pass another number like 4\.0/3\.0 or 16\.0/10\.0, FlexCel will try to create a comment box with that approximate aspect ratio\. Note that the ratio won't be the exact  aspect ratio, just approximate\.|
|const|**dontShrink**|Boolean|If true, the box will grow if the text needs more space, but it won't be made smaller if the text fits in a smaller height than the existing anchor\.|
|const|**adjustment**|Double|The final height will be multiplied by this number\. Because of small differences between how FlexCel and Excel render the text,  it might happen that the size calculated by FlexCel is smaller than what it needs to be to display correctly in Excel\. By setting  this number bigger than 1, you can add a margin for those errors\.|
|const|**adjustmentFixed**|Double|This number will be added to the final calculated height\. Use it to add some margin around the comment box\.|
|const|**anchor**|[TClientAnchor](../../FlexCel.Core/TClientAnchor/index.md)||


## Returns

The new anchor so the size of the box fits the text\.

## Examples

This code will add a comment and resize the box so it fits:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> AddCommentAndResize</span><span style="color:#000000;--shiki-dark:#D4D4D4">(</span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls: TXlsFile; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> aspectRatio: </span><span style="color:#0000FF;--shiki-dark:#569CD6">double</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> col: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">; </span><span style="color:#0000FF;--shiki-dark:#569CD6">const</span><span style="color:#000000;--shiki-dark:#D4D4D4"> text: TRichString);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  comProps: ICommentProperties;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  comProps := TCommentProperties_CreateStandard(row, col, xls);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Create a standard comment box.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  comProps.Anchor := xls.AutofitComment(text, aspectRatio, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1.1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, comProps.Anchor);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Resize it so it fits the text.</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SetComment(row, col, text, </span><span style="color:#A31515;--shiki-dark:#CE9178">''</span><span style="color:#000000;--shiki-dark:#D4D4D4">, comProps);  </span><span style="color:#008000;--shiki-dark:#6A9955">//Add the comment.</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">procedure</span><span style="color:#795E26;--shiki-dark:#DCDCAA"> CreateFileWithComment</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls: TXlsFile;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls := TXlsFile.Create(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, TExcelFileFormat.v2021, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  try</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    AddCommentAndResize(xls, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1.6</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#A31515;--shiki-dark:#CE9178">'This is a long comment so it won''t fit in a standard comment box. '</span><span style="color:#000000;--shiki-dark:#D4D4D4"> + </span><span style="color:#A31515;--shiki-dark:#CE9178">' But by using AutoFitComment, we will resize the box to hold all the text, and have an 1.6 aspect ratio between width and height'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Save(</span><span style="color:#A31515;--shiki-dark:#CE9178">'test.xlsx'</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  finally</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    xls.Free;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TXlsFile](../TXlsFile/index.md)


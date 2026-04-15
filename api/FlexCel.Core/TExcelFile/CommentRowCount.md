---
uid: TExcelFile.CommentRowCount
description: TExcelFile.CommentRowCount
---

# TExcelFile\.CommentRowCount Method

Maximum row index including comments\.


## Remarks

There are 2 groups of Comment related methods\. One is used when you want to find out on a loop all existing comments on  a range, and the other is used to get/set comments at a specified position \(row and col\)\.
To loop among all existing comments, you can use CommentRowCount together with [CommentCountRow](CommentCountRow.md)\.
Do not confuse them, even when they have similar names\. CommentRowCount returns the maximum row with a comment, and [CommentCountRow](CommentCountRow.md) returns the number of comments in a given row\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.CommentRowCount: Integer; virtual; abstract;</code></pre>

## Examples

You can loop on all the comments on a sheet with the following code:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">var</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  row: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  commentIndex: </span><span style="color:#0000FF;--shiki-dark:#569CD6">Int32</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">...</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">  for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> row := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.CommentRowCount </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  begin</span></span>
<span class="line"><span style="color:#AF00DB;--shiki-dark:#C586C0">    for</span><span style="color:#000000;--shiki-dark:#D4D4D4"> commentIndex := </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#0000FF;--shiki-dark:#569CD6"> to</span><span style="color:#000000;--shiki-dark:#D4D4D4"> xls.CommentCountRow(row) </span><span style="color:#AF00DB;--shiki-dark:#C586C0">do</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    begin</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">      DoSomething(xls.GetCommentRow(row, commentIndex));</span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">    end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">    </span></span>
<span class="line"><span style="color:#0000FF;--shiki-dark:#569CD6">  end</span><span style="color:#000000;--shiki-dark:#D4D4D4">;</span></span>
<span class="line"></span></code></pre>



## See also

* [TExcelFile](../TExcelFile/index.md)
* [CommentCountRow](CommentCountRow.md)
* [GetCommentRow](GetCommentRow.md)
* [GetCommentRowCol](GetCommentRowCol.md)
* [GetComment](GetComment.md)
* [SetCommentRow\(Integer, Integer, string, IImageProperties, Boolean\)](SetCommentRow.md#texcelfilesetcommentrowinteger-integer-string-iimageproperties-boolean)
* [SetComment\(Integer, Integer, TRichString\)](SetComment.md#texcelfilesetcommentinteger-integer-trichstring)
* [GetCommentPropertiesRow](GetCommentPropertiesRow.md)
* [SetCommentPropertiesRow](SetCommentPropertiesRow.md)
* [SetCommentProperties](SetCommentProperties.md)


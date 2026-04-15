---
uid: TExcelFile.KeepRowsTogether
description: TExcelFile.KeepRowsTogether
---

# TExcelFile\.KeepRowsTogether Method

Tells FlexCel that it must try to keep together the rows between row1 and row2 \(inclusive\) when printing\.
This method does nothing to the resulting Excel file since this is not an Excel feature\. To actually do something, you need to call [AutoPageBreaks](AutoPageBreaks.md) after calling this method\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.KeepRowsTogether(const row1: Integer; const row2: Integer; const level: Integer; const replaceBiggerLevels: Boolean); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row1**|Integer|First row of the group you want to keep together\.|
|const|**row2**|Integer|Last row of the group you want to keep together\.|
|const|**level**|Integer|Set this parameter to 0 to remove the condition to keep rows together\. Any bigger than zero value will mean that the rows must be kept together\. You can use more than one level to tell FlexCel to try to keep different groups together\.<br />If all rows cannot be kept together in one page, FlexCel will try to keep as much rows with higher levels as possible\. See the example for more information\.|
|const|**replaceBiggerLevels**|Boolean|If true, all existing level values in the row range will be replaced\. If false, the new level values will be written  only if they are bigger than the existing ones\. You can use the false setting to set many values in any order\.<br /><br />For example, if you first call KeepRowsTogether\(2, 3, 5, false\) and then KeepRowsTogether\(1, 10, 1, false\), rows 2 and 3 will keep the level in 5\. If you did so with this parameter true, the second call would replace the levels of rows 2 and 3 to level 1, making all row levels between 1 and 10 equal to 1\.|


## Examples

If you call:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.KeepColsTogether(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.KeepColsTogether(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">2</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>

This will define two groups\. FlexCel will try to keep rows 1 to 10 in one page\. But if this is impossible, it will try to keep at least rows 3 and 4 together\.

Values of the "level" parameter mean the strongness of the link\. Rows with higher level values have a stronger link, and if it is impossible to keep all rows together, FlexCel will try to keep the higher level rows\.

In this case, Rows 3 and 4 have a higher level, so if rows 1 to 10 cannot be kept together in one page, FlexCel will try to keep at least rows 3 and 4\.
Normally you will want to use higher level values completely inside groups with lower levels\.
If we called:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.KeepRowsTogether(</span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">10</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.KeepRowsTogether(</span><span style="color:#098658;--shiki-dark:#B5CEA8">3</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">4</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">, </span><span style="color:#0000FF;--shiki-dark:#569CD6">true</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>

The second call would do nothing, since the level is the same, and rows 1 to 10 are already linked\.


## See also

* [TExcelFile](../TExcelFile/index.md)


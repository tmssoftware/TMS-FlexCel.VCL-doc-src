---
uid: TExcelFile.SendBack
description: TExcelFile.SendBack
---

# TExcelFile\.SendBack Method

Sends the graphical object one layer down\. It will show below and will be covered by image at objectIndex\-1\.


## Remarks

This will change the order of the array,  so after calling SendToBack\(i\), position i will have a new object\.
To move an object 2 steps down the correct code is:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendBack(i);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendBack(i - </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>

and not

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendBack(i);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendBack(i);</span></span>
<span class="line"></span></code></pre>

The second code would actually leave the array unmodified\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SendBack(const objectIndex: Integer); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TExcelFile](../TExcelFile/index.md)
* [SendToBack](SendToBack.md)
* [SendForward](SendForward.md)
* [BringToFront](BringToFront.md)


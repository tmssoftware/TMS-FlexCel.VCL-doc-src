---
uid: TXlsFile.SendForward
description: TXlsFile.SendForward
---

# TXlsFile\.SendForward Method

Sends the graphical object one layer up on the display \(z\-order\) position\. It will show above and will cover the image at objectIndex\+1\.


## Remarks

This will change the order of the array,  so after calling SendForward\(i\), position i will have a new object\.
To move an object 2 steps down the correct code is:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendForward(i);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendForward(i + </span><span style="color:#098658;--shiki-dark:#B5CEA8">1</span><span style="color:#000000;--shiki-dark:#D4D4D4">);</span></span>
<span class="line"></span></code></pre>

and not

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendForward(i);</span></span>
<span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xls.SendForward(i);</span></span>
<span class="line"></span></code></pre>

The second code would actually leave the array unmodified\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SendForward(const objectIndex: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object to move\. \(1 based\)|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.SendToBack](../../FlexCel.Core/TExcelFile/SendToBack.md)
* [TExcelFile.SendBack](../../FlexCel.Core/TExcelFile/SendBack.md)
* [TExcelFile.BringToFront](../../FlexCel.Core/TExcelFile/BringToFront.md)


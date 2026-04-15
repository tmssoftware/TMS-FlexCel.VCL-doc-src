---
uid: TFlxConsts.RowMult
description: TFlxConsts.RowMult
---

# TFlxConsts.RowMult Constant

Multiply by this number to convert pixels to excel row height units\.


## Remarks

1 Height unit= 1/20 pt\. 1pt=1/72 inch\.  At 96ppi, 1 Height Unit= 96/\(72\*20\)pixels \-> 1 pix=\(72\*20\)/96 = 15 Height units\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">const <a href="../TFlxConsts/index.md">TFlxConsts</a>.RowMult = $F;</code></pre>

## Examples

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  RowHeightInPixels := xls.GetRowHeight(Row) / TFlxConsts.RowMult;</span></span>
<span class="line"></span></code></pre>



## See also

* [TFlxConsts](../TFlxConsts/index.md)


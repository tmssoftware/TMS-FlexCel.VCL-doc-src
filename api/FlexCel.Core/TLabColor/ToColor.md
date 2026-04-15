---
uid: TLabColor.ToColor
description: TLabColor.ToColor
---

# TLabColor\.ToColor Method

Returns a system color from this instance\. This method is only needed in C\+\+, in Delphi you can just assign the LabColor to the Color:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  myColor := labColor;</span></span>
<span class="line"></span></code></pre>

Is the same as:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  myColor := labColor.ToColor;</span></span>
<span class="line"></span></code></pre>



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TLabColor/index.md">TLabColor</a>.ToColor: <a href="../TUIColor/index.md">TUIColor</a>;</code></pre>

## See also

* [TLabColor](../TLabColor/index.md)


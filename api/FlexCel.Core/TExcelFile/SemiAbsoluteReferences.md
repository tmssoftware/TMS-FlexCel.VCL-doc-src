---
uid: TExcelFile.SemiAbsoluteReferences
description: TExcelFile.SemiAbsoluteReferences
---

# TExcelFile.SemiAbsoluteReferences Property

When this property is false, inserting and copying ranges will behave the same as it does in Excel\.
When this property is true, absolute references to cells inside the block being copied will be treated as relative\.
For example, if you have:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>A1: 2</span></span>
<span class="line"><span>B1: =$A$1 + $A$57</span></span>
<span class="line"><span></span></span></code></pre>

and you copy the row 1 to row 2, in Excel or FlexCel when this property is false you will get:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>A2: 2</span></span>
<span class="line"><span>B2: =$A$1 + $A$57</span></span>
<span class="line"><span></span></span></code></pre>

When this property is true, you will get:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>A2: 2</span></span>
<span class="line"><span>B2: =$A$2 + $A$57</span></span>
<span class="line"><span></span></span></code></pre>

In the second case, the first reference was updated because it was inside the range being copied, but the second was not\.
This property might be useful when you want to duplicate blocks of cells, but want the absolute references inside it to point to the newer block\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.SemiAbsoluteReferences: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


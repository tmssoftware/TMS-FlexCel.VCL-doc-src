---
uid: TPdfWriter.GetMatrix
description: TPdfWriter.GetMatrix
---

# TPdfWriter\.GetMatrix Method

Returns the drawing matrix in use\. The elements in this matrix are similar to the ones returned by "System\.Drawing\.Drawing2D\.Matrix\.Elements" and have the same meaning\.
**Important remark\. This matrix is the real one, and does not consider things like [YAxisGrowsDown](YAxisGrowsDown.md) or [Scale](Scale.md)\.** You will probably want to use [Transform\(TUIPointF\)](Transform.md#tpdfwritertransformtuipointf) to find out the coordinates of a point\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfWriter/index.md">TPdfWriter</a>.GetMatrix: TArray&lt;Double&gt;;</code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)


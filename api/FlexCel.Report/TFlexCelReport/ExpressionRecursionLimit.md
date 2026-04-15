---
uid: TFlexCelReport.ExpressionRecursionLimit
description: TFlexCelReport.ExpressionRecursionLimit
---

# TFlexCelReport.ExpressionRecursionLimit Property

Defines how much nesting you can have in Expressions before FlexCel throws an error\. You might have an expression like \<\#A> which is defined based in another expression \<\#B> which in turn is defined based in another one that finally might come back to \<\#A> As it is not possible for FlexCel to know if the recursion will finish or  loop forever, it will try until it reaches the limit you set here\. Note that a too big limit could cause a stack overflow\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.ExpressionRecursionLimit: Integer</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


---
uid: TLinkedStyle.AutomaticChoose
description: TLinkedStyle.AutomaticChoose
---

# TLinkedStyle.AutomaticChoose Property

When this property is true \(the default\) FlexCel will automatically choose which linked properties to apply depending on what changes from the base style\. For example, if this style has a different font than the basic style, the font will be not linked, and when you change the base style it will keep the same\.
Excel behaves this way when it adds styles\. To manually choose what the format will affect, set this to none\.
This property doesn't correspond with any Excel property, and it is not stored in the file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TLinkedStyle/index.md">TLinkedStyle</a>.AutomaticChoose: Boolean</code></pre>

## See also

* [TLinkedStyle](../TLinkedStyle/index.md)


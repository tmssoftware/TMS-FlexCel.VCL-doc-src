---
uid: TCellValue.IsError
description: TCellValue.IsError
---

# TCellValue\.IsError Method

Returns true if the cell has an error like \#N/A\! or \#DIV0\!\.
Note that this only applies to error values entered directly in the cell\.
If the cell has a formula that returns \#N/A\!, then the cell has a formula and the formula has an error\. But the cell itself doesn't have an error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCellValue/index.md">TCellValue</a>.IsError: Boolean;</code></pre>

## See also

* [TCellValue](../TCellValue/index.md)


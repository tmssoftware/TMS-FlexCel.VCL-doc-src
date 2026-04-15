---
uid: TFlexCelPrintDocument.CalcPrintArea
description: TFlexCelPrintDocument.CalcPrintArea
---

# TFlexCelPrintDocument\.CalcPrintArea Method

Calculates the actual spreadsheet range that will be printed\. This is given by: 1\)If you specified non zero values on PrintRange, this will be used\.
2\)If any value in PrintRange is zero and there is a Print Area defined on the spreadsheet, the Print Area will be used\.
3\)If there is no PrintRange and no Print Area defined, the visible cells on the sheet will be printed\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TFlexCelPrintDocument/index.md">TFlexCelPrintDocument</a>.CalcPrintArea: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>;</code></pre>

## See also

* [TFlexCelPrintDocument](../TFlexCelPrintDocument/index.md)


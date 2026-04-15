---
uid: TXlsFile.CellIndentationRendering
description: TXlsFile.CellIndentationRendering
---

# TXlsFile.CellIndentationRendering Property

Excel doesn't adapt the cell indentation when changing the print scale\. This means that if a cell indentation is 0\.1 inches at 100%% print scale, it will also be 0\.1 inches at 50%% print scale\. This will break the layout of your files when changing the print scaling, and so by default FlexCel won't behave like Excel here and make the indentation half the size if printing at half the scale\. If you want to mimic the exact Excel behavior, set this property to TCellIndentationRendering\.DontScaleIndentationWithPrintScaleExceptWhenPrintHeadings\.
See ['Cell indentation' in the Api Developer Guide](xref:ApiDeveloperGuide#cell-indentation)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.CellIndentationRendering: <a href="../../FlexCel.Core/TCellIndentationRendering.md">TCellIndentationRendering</a></code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


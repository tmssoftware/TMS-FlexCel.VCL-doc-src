---
uid: TExcelFile.CellIndentationRendering
description: TExcelFile.CellIndentationRendering
---

# TExcelFile.CellIndentationRendering Property

Excel doesn't adapt the cell indentation when changing the print scale\. This means that if a cell indentation is 0\.1 inches at 100%% print scale, it will also be 0\.1 inches at 50%% print scale\. This will break the layout of your files when changing the print scaling, and so by default FlexCel won't behave like Excel here and make the indentation half the size if printing at half the scale\. If you want to mimic the exact Excel behavior, set this property to TCellIndentationRendering\.DontScaleIndentationWithPrintScaleExceptWhenPrintHeadings\.
See ['Cell indentation' in the Api Developer Guide](xref:ApiDeveloperGuide#cell-indentation)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.CellIndentationRendering: <a href="../TCellIndentationRendering.md">TCellIndentationRendering</a></code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


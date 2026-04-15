---
uid: TExcelFile.VirtualCellRead
description: TExcelFile.VirtualCellRead
---

# TExcelFile.VirtualCellRead Event

If you assign this event FlexCel will not load the file into memory when opening a file, allowing you to  open very big files using little memory\. This event will be called for every value read from the file, and then  the value will be discarded, instead of loaded into memory\. Look at ['Virtual mode' in the Performance Guide](xref:PerformanceGuide#virtual-mode) for more information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.VirtualCellRead: TVirtualCellReadEventHandler</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


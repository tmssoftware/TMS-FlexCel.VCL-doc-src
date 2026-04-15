---
uid: TXlsFile.OptionsFullRecalcOnLoad
description: TXlsFile.OptionsFullRecalcOnLoad
---

# TXlsFile.OptionsFullRecalcOnLoad Property

This property tells you if the open file wasn't recalculated when saved\.
If true, the workbook doesn't have recalculated values and will be recalculated when open in Excel\.
This option only applies to xlsx files\.
Note that if you open a file which has FullRecalcOnLoad = true in FlexCel, recalculate it and save it, FlexCel will save the file with FullRecalcOnLoad = false\. To change what FlexCel writes in FullRecalcOnLoad when saving, change [TExcelFile.OptionsFullRecalcOnLoadMode](../../FlexCel.Core/TExcelFile/OptionsFullRecalcOnLoadMode.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.OptionsFullRecalcOnLoad: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


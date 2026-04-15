---
uid: TExcelFile.OptionsFullRecalcOnLoad
description: TExcelFile.OptionsFullRecalcOnLoad
---

# TExcelFile.OptionsFullRecalcOnLoad Property

This property tells you if the open file wasn't recalculated when saved\.
If true, the workbook doesn't have recalculated values and will be recalculated when open in Excel\.
This option only applies to xlsx files\.
Note that if you open a file which has FullRecalcOnLoad = true in FlexCel, recalculate it and save it, FlexCel will save the file with FullRecalcOnLoad = false\. To change what FlexCel writes in FullRecalcOnLoad when saving, change [OptionsFullRecalcOnLoadMode](OptionsFullRecalcOnLoadMode.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.OptionsFullRecalcOnLoad: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


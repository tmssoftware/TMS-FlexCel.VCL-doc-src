---
uid: TExcelFile.RecoveryMode
description: TExcelFile.RecoveryMode
---

# TExcelFile.RecoveryMode Property

When this property is set to true, FlexCel will try to open corrupt files ignoring most of what can be ignored\.
Note that **FlexCel is not a recovery tool** and that this property might be able or not to open a corrupt file\.
Also, even if you are able to open the file with FlexCel, when you save the corrupt file, it might stay corrupt\. FlexCel saves back as much as it can from the original file in order to preserve them, and this means it might save the corrupt parts too\.



Note that when opening a file in recovery mode, the value of [ErrorActions](ErrorActions.md) is ignored, as we will try to ignore as much errors as we can\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.RecoveryMode: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


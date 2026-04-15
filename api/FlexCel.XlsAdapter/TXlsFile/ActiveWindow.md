---
uid: TXlsFile.ActiveWindow
description: TXlsFile.ActiveWindow
---

# TXlsFile.ActiveWindow Property

Gets or sets the active windows to which some sheet and workbook options like zoom will apply\. \(1 based\) Note that spreadsheets normally have a single Window, so this value will most likely be 1 and should stay that way\. If you are working with multiple spreadsheet windows, you can change this property to change the sheet options of a particular window\. The properties that apply to a specific window and are affected by this property mention it on their docs\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.ActiveWindow: Integer</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


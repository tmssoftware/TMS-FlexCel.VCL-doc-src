---
uid: TXlsFile.SheetCodeName
description: TXlsFile.SheetCodeName
---

# TXlsFile.SheetCodeName Property

Returns or sets the codename of a sheet, that is an unique identifier assigned to the sheet when it is created\.
Codenames are useful because they never change once the file is created, and they are what macros reference\.
**Very important\! We don't support changing codenames if the file has macros, because we can't modify the required macros to use the modified codename\. Also, Excel 2003 or older will ignore the codename if the file doesn't have macros\.
Excel 2007 or newer will preserve the codenames even if the file doesn't have macros\.**

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.SheetCodeName: string</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


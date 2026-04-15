---
uid: TXlsFile.SheetID
description: TXlsFile.SheetID
---

# TXlsFile.SheetID Property

Returns an unique identifier for the active sheet\. This is a value that is only used by FlexCel, and you can use it together with [TExcelFile.GetSheetIndexFromID](../../FlexCel.Core/TExcelFile/GetSheetIndexFromID.md) to retrieve a sheet after deleting or adding sheets\.
While normally you can use [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) to store and retrieve a sheet, if you plan to delete or add sheets before restoring the active sheet, the  stored ActiveSheet could become invalid\. **Note that this is a value internal for FlexCel, and not stored in the xls/x file\.** SheetIDs will change every time you open the file\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.SheetID: TGUID</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


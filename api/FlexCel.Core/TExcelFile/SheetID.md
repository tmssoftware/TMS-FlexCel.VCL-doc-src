---
uid: TExcelFile.SheetID
description: TExcelFile.SheetID
---

# TExcelFile.SheetID Property

Returns an unique identifier for the active sheet\. This is a value that is only used by FlexCel, and you can use it together with [GetSheetIndexFromID](GetSheetIndexFromID.md) to retrieve a sheet after deleting or adding sheets\.
While normally you can use [ActiveSheet](ActiveSheet.md) to store and retrieve a sheet, if you plan to delete or add sheets before restoring the active sheet, the  stored ActiveSheet could become invalid\. **Note that this is a value internal for FlexCel, and not stored in the xls/x file\.** SheetIDs will change every time you open the file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.SheetID: TGUID</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


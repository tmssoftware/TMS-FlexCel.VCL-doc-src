---
uid: TXlsFile.CopyColFormats
description: TXlsFile.CopyColFormats
---

# TXlsFile\.CopyColFormats Method

Copies the column definitions, that is formats, widths, hidden/visible, etc from one workbook or sheet to another\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.CopyColFormats(const sourceWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const sourceSheet: Integer; const sourceCol: Integer; const destCol: Integer; const colCount: Integer); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sourceWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|The workbook from where the column formats will be copied\. If you set this to null, the column formats will be copied from the same file\.|
|const|**sourceSheet**|Integer|Sheet in the source workbook from where we will copy the column formats\.|
|const|**sourceCol**|Integer|First column format to copy|
|const|**destCol**|Integer|First column where the format will be copied\.|
|const|**colCount**|Integer|Number of columns to copy\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


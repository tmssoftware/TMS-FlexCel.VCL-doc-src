---
uid: TXlsFile.GetSheetIndex
description: TXlsFile.GetSheetIndex
---

# TXlsFile\.GetSheetIndex Method

Finds a sheet name on the workbook and returns its index\.
Depending on the "throwException" parameter, this method will raise an exception or return \-1 if the sheet does not exist\.
To change the active sheet by the name, use [TExcelFile.ActiveSheetByName](../../FlexCel.Core/TExcelFile/ActiveSheetByName.md)\. See also [TExcelFile.GetSheetName](../../FlexCel.Core/TExcelFile/GetSheetName.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetSheetIndex(const sheetName: string; const throwException: Boolean): Integer; overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetName**|string|Sheet you want to find\.|
|const|**throwException**|Boolean|When sheetName does not exist, having throwException = true will raise an Exception\. throwException = false will  return \-1 if the sheet is not found\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.DeleteSheet
description: TXlsFile.DeleteSheet
---

# TXlsFile\.DeleteSheet Method

Deletes sheet aSheet and aSheetCount\-1 sheets more to the right\.
It will change all formula references to that sheet to invalid, and might change the active sheet so it remains valid\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.DeleteSheet(const aSheet: Integer; const aSheetCount: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheet**|Integer|First sheet to delete \(1\-based\)\.|
|const|**aSheetCount**|Integer|The number of sheets to delete\.|


## See also

* [TXlsFile](../TXlsFile/index.md)
* [TExcelFile.ClearSheet](../../FlexCel.Core/TExcelFile/ClearSheet.md)


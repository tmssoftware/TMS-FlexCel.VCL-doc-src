---
uid: TXlsFile.GetSheetIndexFromID
description: TXlsFile.GetSheetIndexFromID
---

# TXlsFile\.GetSheetIndexFromID Method

Returns the ActiveSheet for a stored [TExcelFile.SheetID](../../FlexCel.Core/TExcelFile/SheetID.md)\.
You can use this method together with [TExcelFile.SheetID](../../FlexCel.Core/TExcelFile/SheetID.md) to save and restore an ActiveSheet when you are adding or removing sheets\.


If the sheet ID doesn't exist, this method will return 0\.



## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetSheetIndexFromID(const aSheetID: TGUID): Integer; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetID**|TGUID||


## See also

* [TXlsFile](../TXlsFile/index.md)


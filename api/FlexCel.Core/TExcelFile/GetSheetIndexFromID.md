---
uid: TExcelFile.GetSheetIndexFromID
description: TExcelFile.GetSheetIndexFromID
---

# TExcelFile\.GetSheetIndexFromID Method

Returns the ActiveSheet for a stored [SheetID](SheetID.md)\.
You can use this method together with [SheetID](SheetID.md) to save and restore an ActiveSheet when you are adding or removing sheets\.


If the sheet ID doesn't exist, this method will return 0\.



## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetSheetIndexFromID(const aSheetID: TGUID): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSheetID**|TGUID||


## See also

* [TExcelFile](../TExcelFile/index.md)


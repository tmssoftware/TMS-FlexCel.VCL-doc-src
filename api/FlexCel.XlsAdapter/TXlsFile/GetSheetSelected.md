---
uid: TXlsFile.GetSheetSelected
description: TXlsFile.GetSheetSelected
---

# TXlsFile\.GetSheetSelected Method

Returns true if a sheet is selected, false otherwise\. Note that you might select many sheets in Excel by shift or ctrl\-clicking the sheet tabs\. Also note that when changing the [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md), the sheet selected will be reset to the active sheet\.
So if you want to find out which sheets are selected in a file, you should call this method after opening the file but before changing the active sheet\.
This property can work in different windows depending on the value of [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetSheetSelected(const sheetIndex: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetIndex**|Integer|Sheet index for the tab we want to know if it is selected\. 1 based\.|


## Returns

True is the sheet is selected, false otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)


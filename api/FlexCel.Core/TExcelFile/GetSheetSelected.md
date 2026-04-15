---
uid: TExcelFile.GetSheetSelected
description: TExcelFile.GetSheetSelected
---

# TExcelFile\.GetSheetSelected Method

Returns true if a sheet is selected, false otherwise\. Note that you might select many sheets in Excel by shift or ctrl\-clicking the sheet tabs\. Also note that when changing the [ActiveSheet](ActiveSheet.md), the sheet selected will be reset to the active sheet\.
So if you want to find out which sheets are selected in a file, you should call this method after opening the file but before changing the active sheet\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetSheetSelected(const sheetIndex: Integer): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetIndex**|Integer|Sheet index for the tab we want to know if it is selected\. 1 based\.|


## Returns

True is the sheet is selected, false otherwise\.

## See also

* [TExcelFile](../TExcelFile/index.md)


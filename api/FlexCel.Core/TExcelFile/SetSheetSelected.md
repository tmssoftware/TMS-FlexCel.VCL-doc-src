---
uid: TExcelFile.SetSheetSelected
description: TExcelFile.SetSheetSelected
---

# TExcelFile\.SetSheetSelected Method

This method will set a sheet tab as selected\. Note that this is different from [ActiveSheet](ActiveSheet.md) in that you might have only a single active sheet, but you might select many tabs by ctrl\-clicking them\. Also note that whenever you change the [ActiveSheet](ActiveSheet.md), the selected sheets will be reset to the active sheet only\. So if you want to save a file with more than one selected sheet, you should call this method **after** the last call to activesheet\.
This property can work in different windows depending on the value of [ActiveWindow](ActiveWindow.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetSheetSelected(const sheetIndex: Integer; const selected: Boolean); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**sheetIndex**|Integer|Sheet index for the sheet we want to select or unselect\.\(1 based\)|
|const|**selected**|Boolean|If true the sheet will be selected, otherwise it will be unselected\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


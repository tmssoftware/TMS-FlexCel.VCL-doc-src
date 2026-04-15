---
uid: TSheetSelector.DrawOneSheetSelector
description: TSheetSelector.DrawOneSheetSelector
---

# TSheetSelector\.DrawOneSheetSelector Method

Override this method on a child class if you want to completely customize how the Sheet Selector is drawn\.
Normally when deriving from [TStandardSheetSelector](../TStandardSheetSelector/index.md) you can just change the CSS properties of this class to customize the SheetSelector, but you can use this if you want to  provide a completely different selector\. You can use the [Links](Links.md) collection to know which hyperlinks to place in each place\.
Note that different from [BeforeDrawOneSheetSelector](BeforeDrawOneSheetSelector.md), this method is **only** called for the positions where the selector has to be rendered\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TSheetSelector/index.md">TSheetSelector</a>.DrawOneSheetSelector(const xls: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const Position: <a href="../TSheetSelectorPosition.md">TSheetSelectorPosition</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|ExcelFile we are exporting\. It is positioned on the sheet we are exporting, but its active sheet can be changed on this method and there is no need to restore it\. It will be restored by the framework\.|
|const|**Position**|[TSheetSelector&#8203;Position](../TSheetSelectorPosition.md)|Position where the sheet selector will be placed\. Note that this method will always be called with only one value, but it might be called more than once if constants in the TSheetSelectorPosition enumeration are or'ed together\.|


## See also

* [TSheetSelector](../TSheetSelector/index.md)


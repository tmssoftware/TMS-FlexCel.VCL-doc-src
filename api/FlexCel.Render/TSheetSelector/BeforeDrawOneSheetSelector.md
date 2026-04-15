---
uid: TSheetSelector.BeforeDrawOneSheetSelector
description: TSheetSelector.BeforeDrawOneSheetSelector
---

# TSheetSelector\.BeforeDrawOneSheetSelector Method

Use this method to customize actions to do after the SheetSelector is drawn\.
In the [TStandardSheetSelector](../TStandardSheetSelector/index.md) implementation, this method is used to add a table for layout if [TStandardSheetSelector.LayoutTable](../TStandardSheetSelector/LayoutTable.md) is true\.
Note that this method is called once for each of the possible positions of Reference, even if you do not need to draw a selector in that position\.
The order in which this method will be called is: Top, Left, Right, Bottom\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TSheetSelector/index.md">TSheetSelector</a>.BeforeDrawOneSheetSelector(const Reference: <a href="../TSheetSelectorPosition.md">TSheetSelectorPosition</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Reference**|[TSheetSelector&#8203;Position](../TSheetSelectorPosition.md)|The position of the SheetSelector that is being created\.<br />you can use [SheetSelectorPosition](SheetSelectorPosition.md) to know if this is one of the selectors you need to render\.|


## See also

* [TSheetSelector](../TSheetSelector/index.md)


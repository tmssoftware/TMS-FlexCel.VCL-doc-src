---
uid: TSheetSelector
description: TSheetSelector
---

# TSheetSelector Class

Abstract class to implement a Sheet Selector\. Derive from this class for example to implement tabs with images\. For a standard implementation using CSS Tabs and divs, use [TStandardSheetSelector](../TStandardSheetSelector/index.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TSheetSelector = class(TCoreSheetSelector);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Constructs a new TSheetSelector instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[GetHtmlSheet&#8203;Name&#8203;From&#8203;Excel](GetHtmlSheetNameFromExcel.md)|Returns the html sheet name from the Excel sheet name\. Returns empty if the sheet doesn't exist\.<br />|
|[WriteLn](WriteLn.md)|Use this method to write a line inside the stream when overriding this class\.<br />|
|[EncodeAsHtml](EncodeAsHtml.md)|This method will encode a string so it is valid html\. For example, it will replace "&amp;" by "&amp;amp;" in the text\.<br />|
|[AfterDrawOne&#8203;Sheet&#8203;Selector](AfterDrawOneSheetSelector.md)|Use this method to customize actions to do before the SheetSelector is drawn\.<br />In the [TStandardSheet&#8203;Selector](../TStandardSheetSelector/index.md) implementation, this method is used to add a table for layout if [TStandardSheet&#8203;Selector.&#8203;Layout&#8203;Table](../TStandardSheetSelector/LayoutTable.md) is true\.<br />Note that this method is called once for each of the possible positions of Reference, even if you do not need to draw a selector in that position\.<br />The order in which this method will be called is: Top, Left, Right, Bottom\.<br />|
|[BeforeDrawOne&#8203;Sheet&#8203;Selector](BeforeDrawOneSheetSelector.md)|Use this method to customize actions to do after the SheetSelector is drawn\.<br />In the [TStandardSheet&#8203;Selector](../TStandardSheetSelector/index.md) implementation, this method is used to add a table for layout if [TStandardSheet&#8203;Selector.&#8203;Layout&#8203;Table](../TStandardSheetSelector/LayoutTable.md) is true\.<br />Note that this method is called once for each of the possible positions of Reference, even if you do not need to draw a selector in that position\.<br />The order in which this method will be called is: Top, Left, Right, Bottom\.<br />|
|[DrawOneSheetSelector](DrawOneSheetSelector.md)|Override this method on a child class if you want to completely customize how the Sheet Selector is drawn\.<br />Normally when deriving from [TStandardSheet&#8203;Selector](../TStandardSheetSelector/index.md) you can just change the CSS properties of this class to customize the SheetSelector, but you can use this if you want to  provide a completely different selector\. You can use the [Links](Links.md) collection to know which hyperlinks to place in each place\.<br />Note that different from [BeforeDrawOne&#8203;Sheet&#8203;Selector](BeforeDrawOneSheetSelector.md)[...[more]](DrawOneSheetSelector.md)|
|[WriteCssClasses](WriteCssClasses.md)|This method is in charge of writing the style definitions in the header of the html file\.<br />Note that when deriving from [TStandardSheet&#8203;Selector](../TStandardSheetSelector/index.md) you normally do not need to override this method, you can just change the CSS properties of this class\.<br />You can override this method if you want full control on how to export the classes\.<br />|


## Properties

|Name|Description|
|---|---|
|[SheetSelector&#8203;Position](SheetSelectorPosition.md)|An enumerator defining all the positions where the SheetSelector will be drawn\.Read it to know where to draw the selector\.<br />|
|[Links](Links.md)|A list of links that should go in the sheet selector, one per tab\. Use them when creating your own sheet selector to know where to point the link in the tabs to\.<br />|



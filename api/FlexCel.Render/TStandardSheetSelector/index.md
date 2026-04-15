---
uid: TStandardSheetSelector
description: TStandardSheetSelector
---

# TStandardSheetSelector Class

Implements a standard sheet selector \(with CSS tabs\) that will allow you to change the page when exporting multiple sheets\.
You can customize its default behavior by altering the CSS properties, or by inheriting from it and replacing the virtual methods\.
If you want to create a completely new type of sheet selector, derive it from [TSheetSelector](../TSheetSelector/index.md) instead of this class\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TStandardSheetSelector = class(<a href="../TSheetSelector/index.md">TSheetSelector</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Constructs a new TStandardSheet&#8203;Selector instance\.<br />|


## Methods

|Name|Description|
|---|---|
|[OnSheetSelectorEntry](OnSheetSelectorEntry.md)|Replace this event when creating a custom descendant of TStandardSheet&#8203;Selector\.&#8203;<br />|
|[ReplaceMacros](ReplaceMacros.md)|This is an utility method that will replace all the \<\#\.\.\.> macros inside a tag by its values\.<br />Normally you do not need to call this method, since it is called automatically by [WriteOneCssRule](WriteOneCssRule.md)|
|[WriteOneCssRule](WriteOneCssRule.md)|This method is an utility to write one rule in a TStandarSheet&#8203;Selector&#8203;Styles class\.<br />|
|[WriteOneCssClass](WriteOneCssClass.md)|This method is an utility to write all the classes of an TStandardSheet&#8203;Selector&#8203;Styles class\.<br />|
|[BeforeDrawOne&#8203;Sheet&#8203;Selector](BeforeDrawOneSheetSelector.md)|This method is overriden to add a table for layout when [LayoutTable](LayoutTable.md) is true\.<br />See the documentation in [TSheetSelector.&#8203;Before&#8203;Draw&#8203;OneSheet&#8203;Selector](../TSheetSelector/BeforeDrawOneSheetSelector.md) for more information on this method\.<br />|
|[AfterDrawOne&#8203;Sheet&#8203;Selector](AfterDrawOneSheetSelector.md)|This method is overridden to add a table for layout when [LayoutTable](LayoutTable.md) is true\.<br />See the documentation in [TSheetSelector.&#8203;After&#8203;Draw&#8203;OneSheet&#8203;Selector](../TSheetSelector/AfterDrawOneSheetSelector.md) for more information on this method\.<br />|
|[DrawOneSheetSelector](DrawOneSheetSelector.md)|This method overrides the abstract parent to provide a CSS implementation for tabs\.<br />Override this method on a child class if you want to completely customize how the Sheet Selector is drawn\.<br />Normally you can just change the CSS properties of this class to customize the SheetSelector, but you can use this if you want to  provide a completely different selector\. You can use the [TSheetSelector.Links](../TSheetSelector/Links.md) collection to know which hyperlinks to place in each place\.<br />|
|[WriteCssClasses](WriteCssClasses.md)|This method is in charge of writing the style definitions in the header of the html file\.<br />Note that you normally do not need to override this method, you can just change the CSS properties of this class\.<br />You can override this method if you want full control on how to export the classes\.<br />|


## Properties

|Name|Description|
|---|---|
|[CssGeneral](CssGeneral.md)|Style to be applied to the selector\. This is a general setting, you can later further customize the style when the selector is at the Left, Top, Right or Bottom with the corresponding [CssWhenLeft](CssWhenLeft.md), [CssWhenTop](CssWhenTop.md), [CssWhenRight](CssWhenRight.md) and [CssWhenBottom](CssWhenBottom.md) properties\.<br />|
|[CssWhenLeft](CssWhenLeft.md)|Specific style to be applied to the selector when it goes at the left\. This style will override the style you specify with [CssGeneral](CssGeneral.md)|
|[CssWhenTop](CssWhenTop.md)|Specific style to be applied to the selector when it goes at the top\. This style will override the style you specify with [CssGeneral](CssGeneral.md)|
|[CssWhenRight](CssWhenRight.md)|Specific style to be applied to the selector when it goes at the right\. This style will override the style you specify with [CssGeneral](CssGeneral.md)|
|[CssWhenBottom](CssWhenBottom.md)|Specific style to be applied to the selector when it goes at the bottom\. This style will override the style you specify with [CssGeneral](CssGeneral.md)|
|[CssStyleSheetContent](CssStyleSheetContent.md)|Style to be applied to the sheet content\.<br />|
|[CssStyleLayoutTable](CssStyleLayoutTable.md)|Style to be applied to the layout table if [LayoutTable](LayoutTable.md) is true\.<br />|
|[CssTags](CssTags.md)|This property has a list of Macros that you can use in the CSS definitions\. You can reference this value in the CSS properties by using \<\#variable><br /><br />For example, you could set a Macro "Mycolor" with CssTags\.&#8203;Add\(&#8203;"mycolor"&#8203;, "red"\); and then define a CssProperty: CssWhenTop\.Main = "background\-&#8203;color:&#8203;\<&#8203;\#&#8203;mycolor>&#8203;";<br /><br /><br />This method by default contains the following Macros:[...[more]](CssTags.md)<br /><br /><br />You can modify those Macros or add your own definitions here and use them when defining your CSS\.<br /><br />[...[more]](CssTags.md)|
|[LayoutTable](LayoutTable.md)|When this property is true \(the default\), both selectors at the left and at the right will be layed out in a table\.<br />This has the advantage that block will not wrap down when resizing the window\. But if you would prefer not to use tables for layout, you can turn this property off, and the layout will be pure CSS \(and it will wrap down when there is not enough space\)\.<br />If you do not have a selector in the left or the right this property does nothing\.<br />|
|[UseSheetTabColors](UseSheetTabColors.md)|When true \(the default\) and the sheets have a tab color defined in Excel, FlexCel will use this color to render the sheet tabs\.<br />If false, the default tab color will be used\. Note that if the sheets don't have a color defined in Excel, also the default tab color will be used\.<br />|


## Events

|Name|Description|
|---|---|
|[SheetSelectorEntry](SheetSelectorEntry.md)|Use this event to customize the text and link on the individual tabs\. The tab style itself must be modified with the CSS properties\.<br />|



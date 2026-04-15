---
uid: TNamedRangeExportEventArgs
description: TNamedRangeExportEventArgs
---

# TNamedRangeExportEventArgs Class

Arguments passed on [TFlexCelHtmlExport.OnNamedRangeExport](../TFlexCelHtmlExport/OnNamedRangeExport.md),

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">TNamedRangeExportEventArgs = class(EventArgs);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new Argument\.<br />|


## Properties

|Name|Description|
|---|---|
|[Workbook](Workbook.md)|ExcelFile with the name, positioned in the sheet that we are rendering\.<br />Make sure if you modify ActiveSheet of this instance to restore it back to the original value before exiting the event\.<br />|
|[Sheet](Sheet.md)|Sheet index \(1 based\) of the html cell we are exporting\.<br />|
|[Row](Row.md)|Row index \(1 based\) of the html cell we are exporting\. This number should be the same as the first row in the [NamedRange](NamedRange.md)\.<br />|
|[Col](Col.md)|Column index \(1 based\) of the html cell we are exporting\. This number should be the same as the first column in the [NamedRange](NamedRange.md)\.<br />|
|[NamedRange](NamedRange.md)|Named range that is being exported\.<br />|
|[NameId](NameId.md)|This property is by default the same as [NamedRange](NamedRange.md)\.Name\.  If you want to change the id of the span that will be exported to HTML, change it to the new value\. To not export this name, set it to null\.<br />|



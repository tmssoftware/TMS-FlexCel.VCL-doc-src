---
uid: TFlexCelPdfExport.Export
description: TFlexCelPdfExport.Export
---

# TFlexCelPdfExport\.Export Method

## Overloads

* [TFlexCelPdfExport\.Export\(TStream\)](#tflexcelpdfexportexporttstream)
* [TFlexCelPdfExport\.Export\(string\)](#tflexcelpdfexportexportstring)

# TFlexCelPdfExport\.Export\(TStream\)
Exports the active sheet of the associated xls workbook to a stream\.


## Remarks

This method is a shortcut for calling [BeginExport](BeginExport.md)/ [ExportSheet](ExportSheet.md)/[EndExport](EndExport.md)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.Export(const pdfStream: TStream); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**pdfStream**|TStream|Stream where the result will be written\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)

# TFlexCelPdfExport\.Export\(string\)
Exports the active sheet of the associated xls workbook to a file\.


## Remarks

This method is a shortcut for calling [BeginExport](BeginExport.md)/ [ExportSheet](ExportSheet.md)/[EndExport](EndExport.md)\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.Export(const fileName: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fileName**|string|File to export\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


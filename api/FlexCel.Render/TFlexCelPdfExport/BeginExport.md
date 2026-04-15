---
uid: TFlexCelPdfExport.BeginExport
description: TFlexCelPdfExport.BeginExport
---

# TFlexCelPdfExport\.BeginExport Method

Initializes the PDF exporting to a new file\. After calling this method you can call [ExportSheet](ExportSheet.md) to export different xls files to the same pdf, or [ExportAllVisibleSheets\(Boolean, string\)](ExportAllVisibleSheets.md#tflexcelpdfexportexportallvisiblesheetsboolean-string)\.
You should always end the document with a call to [EndExport](EndExport.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.BeginExport(const pdfStream: TStream);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**pdfStream**|TStream|Stream that will contain the new pdf file\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


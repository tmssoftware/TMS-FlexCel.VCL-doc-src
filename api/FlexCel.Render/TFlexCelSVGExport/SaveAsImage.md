---
uid: TFlexCelSVGExport.SaveAsImage
description: TFlexCelSVGExport.SaveAsImage
---

# TFlexCelSVGExport\.SaveAsImage Method

Saves the current Excel file on an SVG image stream\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelSVGExport/index.md">TFlexCelSVGExport</a>.SaveAsImage(const saveParameters: TProc&lt;<a href="../TSVGExportParameters/index.md">TSVGExportParameters</a>&gt;);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**saveParameters**|TProc\<[TSVGExportParameters](../TSVGExportParameters/index.md)>|Action that will be called once for every page to export\. When this action is called you can  assign a file name for the image, a title and description, cancel the export, etc\.|


## See also

* [TFlexCelSVGExport](../TFlexCelSVGExport/index.md)


---
uid: TPageEventArgs.Create
description: TPageEventArgs.Create
---

# TPageEventArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TPageEventArgs/index.md">TPageEventArgs</a>.Create(const aPdfExport: TObject; const aWorkbook: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const aCurrentSheet: Integer; const aPdfWriter: <a href="../../FlexCel.Pdf/TPdfWriter/index.md">TPdfWriter</a>; const aCurrentPage: Integer; const aCurrentPageInSheet: Integer);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aPdfExport**|TObject|The PdfExport component which is doing the export\.|
|const|**aWorkbook**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|Excel file that is being exported\.|
|const|**aCurrentSheet**|Integer|Sheet that we are currently exporting\.|
|const|**aPdfWriter**|[TPdfWriter](../../FlexCel.Pdf/TPdfWriter/index.md)|The file we are processing\.|
|const|**aCurrentPage**|Integer|The page that is being generated\.|
|const|**aCurrentPageInSheet**|Integer|The page in the current sheet that is being generated\.|


## See also

* [TPageEventArgs](../TPageEventArgs/index.md)


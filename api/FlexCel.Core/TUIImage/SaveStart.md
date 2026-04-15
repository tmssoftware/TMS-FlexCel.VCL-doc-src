---
uid: TUIImage.SaveStart
description: TUIImage.SaveStart
---

# TUIImage\.SaveStart Method

Starts saving a multi page image\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TUIImage/index.md">TUIImage</a>.SaveStart(const outStream: TStream; const ExportType: <a href="../TImageExportType.md">TImageExportType</a>; const totalPages: Integer): <a href="../TUIMultiPageSaver/index.md">TUIMultiPageSaver</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**outStream**|TStream|Stream where the image will be saved\.|
|const|**ExportType**|[TImageExportType](../TImageExportType.md)|Format for the exported images\.|
|const|**totalPages**|Integer|Number of pages to export\.|


## Returns

Image state that will be used when saving the other pages\.

## See also

* [TUIImage](../TUIImage/index.md)


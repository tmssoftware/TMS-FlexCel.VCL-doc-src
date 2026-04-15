---
uid: TGetImageDataEventArgs.Create
description: TGetImageDataEventArgs.Create
---

# TGetImageDataEventArgs\.Create Constructor

Creates a new Argument\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TGetImageDataEventArgs/index.md">TGetImageDataEventArgs</a>.Create(const aExcelFile: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; const aImageName: string; const aImageData: TBytes; const aHeight: Double; const aWidth: Double);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aExcelFile**|[TExcelFile](../../FlexCel.Core/TExcelFile/index.md)|The file we are processing\.|
|const|**aImageName**|string|The name of the image on the Excel sheet\. Use it to identify it\.|
|const|**aImageData**|TBytes|The image data\.|
|const|**aHeight**|Double|The height of the image in pixels\. Change it to resize the image\.|
|const|**aWidth**|Double|The width of the image in pixels\. Change it to resize the image\.|


## See also

* [TGetImageDataEventArgs](../TGetImageDataEventArgs/index.md)


---
uid: TImageInformationEventArgs.ImageLink
description: TImageInformationEventArgs.ImageLink
---

# TImageInformationEventArgs.ImageLink Property

The link that will be inserted in the html file\. Change it if you change the default image location\.
Set it to null to not add a link to this image in the generated html file\. If you want to avoid exporting all images, you can use [THidePrintObjects](../../FlexCel.Core/THidePrintObjects.md) for that\. But if you just want to avoid exporting one image in a file, you can do it by setting [ImageStream](ImageStream.md), [ImageFile](ImageFile.md) and this property to null\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TImageInformationEventArgs/index.md">TImageInformationEventArgs</a>.ImageLink: string</code></pre>

## See also

* [TImageInformationEventArgs](../TImageInformationEventArgs/index.md)


---
uid: TImageInformationEventArgs.ImageFile
description: TImageInformationEventArgs.ImageFile
---

# TImageInformationEventArgs.ImageFile Property

The file where the image will be saved\. If [ImageStream](ImageStream.md) is not null, this property will do nothing\.
If both this property and [ImageStream](ImageStream.md) are null, the image will not be saved\.
When saving as MHTML this parameter does nothing, since all images will be saved in the same MTHML stream\.


## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TImageInformationEventArgs/index.md">TImageInformationEventArgs</a>.ImageFile: string</code></pre>

## See also

* [TImageInformationEventArgs](../TImageInformationEventArgs/index.md)


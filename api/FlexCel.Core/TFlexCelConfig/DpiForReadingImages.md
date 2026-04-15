---
uid: TFlexCelConfig.DpiForReadingImages
description: TFlexCelConfig.DpiForReadingImages
---

# TFlexCelConfig.DpiForReadingImages Property

Allows you to set a DPI for all images FlexCel is importing\. If this value is 0 \(the default\), then FlexCel will try to read the image resolution from the files themselves, if the files have a resolution saved\. If there is no resolution saved with the image, FlexCel will assume the images have the screen resolution\. When you set this property to a non 0 value \(like 96 for example\), then FlexCel will assume this is the resolution of the images it is reading, ignoring any resolution stored in the file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelConfig/index.md">TFlexCelConfig</a>.DpiForReadingImages: Double</code></pre>

## See also

* [TFlexCelConfig](../TFlexCelConfig/index.md)


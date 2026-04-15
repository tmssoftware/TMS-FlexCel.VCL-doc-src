---
uid: TDrawingColor.GetComponents
description: TDrawingColor.GetComponents
---

# TDrawingColor\.GetComponents Method

Returns R, G and B components of the color\. If this is a theme or indexed color, it will be converted to RGB before getting the components\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TDrawingColor/index.md">TDrawingColor</a>.GetComponents(const xls: TCoreExcelFile; out R: Byte; out G: Byte; out B: Byte);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|ExcelFile that will be used to know the palette and themes of the file for indexed/themed colors\.|
|out|**R**|Byte|Returns the red component of the color\.|
|out|**G**|Byte|Returns the green component of the color\.|
|out|**B**|Byte|Returns the blue component of the color\.|


## See also

* [TDrawingColor](../TDrawingColor/index.md)


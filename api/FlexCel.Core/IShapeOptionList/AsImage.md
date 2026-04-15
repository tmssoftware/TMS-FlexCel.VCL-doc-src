---
uid: IShapeOptionList.AsImage
description: IShapeOptionList.AsImage
---

# IShapeOptionList\.AsImage Method

Returns a byte array with the image if it exists, otherwise null\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. In those cases, for backward compatibility reasons, this method will return the PNG image\. To get the SVG, call [AsImageAlternate](AsImageAlternate.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsImage(const xls: TCoreExcelFile; const objectPath: string; const key: <a href="../TShapeOption.md">TShapeOption</a>): TBytes; overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|File with the images\.|
|const|**objectPath**|string|Object path to the image\.|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)


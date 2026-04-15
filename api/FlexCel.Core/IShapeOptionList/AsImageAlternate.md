---
uid: IShapeOptionList.AsImageAlternate
description: IShapeOptionList.AsImageAlternate
---

# IShapeOptionList\.AsImageAlternate Method

Returns a byte array with the image if it exists, otherwise null\.
Note that for SVG images, xlsx files store both a PNG and SVG image\. In those cases, this method will return the SVG image\. To get the PNG, call [AsImage](AsImage.md)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../IShapeOptionList/index.md">IShapeOptionList</a>.AsImageAlternate(const xls: TCoreExcelFile; const objectPath: string; const key: <a href="../TShapeOption.md">TShapeOption</a>): TBytes; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**xls**|TCoreExcelFile|File with the images\.|
|const|**objectPath**|string|Object path to the image\.|
|const|**key**|[TShapeOption](../TShapeOption.md)|Property Name\.|


## See also

* [IShapeOptionList](../IShapeOptionList/index.md)


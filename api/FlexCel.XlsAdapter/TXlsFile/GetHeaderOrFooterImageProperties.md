---
uid: TXlsFile.GetHeaderOrFooterImageProperties
description: TXlsFile.GetHeaderOrFooterImageProperties
---

# TXlsFile\.GetHeaderOrFooterImageProperties Method

Returns the image position and size\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetHeaderOrFooterImageProperties(const headerAndFooterKind: <a href="../../FlexCel.Core/THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../../FlexCel.Core/THeaderAndFooterPos.md">THeaderAndFooterPos</a>): <a href="../../FlexCel.Core/IHeaderOrFooterImageProperties/index.md">IHeaderOrFooterImageProperties</a>; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooterKind.md)|Type of page for which we want to retrieve the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../../FlexCel.Core/THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../../FlexCel.Core/THeaderAndFooterPos.md)|Section of the header or footer for which we want to retrieve the image properties\.|


## Returns

Image properties\. Null if there is no image on this section\.

## See also

* [TXlsFile](../TXlsFile/index.md)


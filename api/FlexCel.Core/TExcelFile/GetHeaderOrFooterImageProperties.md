---
uid: TExcelFile.GetHeaderOrFooterImageProperties
description: TExcelFile.GetHeaderOrFooterImageProperties
---

# TExcelFile\.GetHeaderOrFooterImageProperties Method

Returns the image position and size\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetHeaderOrFooterImageProperties(const headerAndFooterKind: <a href="../THeaderAndFooterKind.md">THeaderAndFooterKind</a>; const section: <a href="../THeaderAndFooterPos.md">THeaderAndFooterPos</a>): <a href="../IHeaderOrFooterImageProperties/index.md">IHeaderOrFooterImageProperties</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**headerAndFooterKind**|[THeaderAndFooterKind](../THeaderAndFooterKind.md)|Type of page for which we want to retrieve the image\. You will normally get this value from [THeaderAndFooter.GetHeaderAndFooterKind](../THeaderAndFooter/GetHeaderAndFooterKind.md)\.|
|const|**section**|[THeaderAndFooterPos](../THeaderAndFooterPos.md)|Section of the header or footer for which we want to retrieve the image properties\.|


## Returns

Image properties\. Null if there is no image on this section\.

## See also

* [TExcelFile](../TExcelFile/index.md)


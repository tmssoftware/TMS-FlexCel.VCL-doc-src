---
uid: TPdfWriter.Hyperlink
description: TPdfWriter.Hyperlink
---

# TPdfWriter\.Hyperlink Method

## Overloads

* [TPdfWriter\.Hyperlink\(Double, Double, Double, Double, string\)](#tpdfwriterhyperlinkdouble-double-double-double-string)
* [TPdfWriter\.Hyperlink\(Double, Double, Double, Double, TUri\)](#tpdfwriterhyperlinkdouble-double-double-double-turi)
* [TPdfWriter\.Hyperlink\(Double, Double, Double, Double, Integer, Double, Double\)](#tpdfwriterhyperlinkdouble-double-double-double-integer-double-double)

# TPdfWriter\.Hyperlink\(Double, Double, Double, Double, string\)
Creates a Hyperlink on the selected region with the specified Url\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.Hyperlink(const x: Double; const y: Double; const width: Double; const height: Double; const url: string); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x**|Double|x coord\.|
|const|**y**|Double|y coord\.|
|const|**width**|Double|Width of the region\.|
|const|**height**|Double|Height of the region\.|
|const|**url**|string|Url where to navigate to\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.Hyperlink\(Double, Double, Double, Double, TUri\)
Creates a Hyperlink on the selected region with the specified Url\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.Hyperlink(const x: Double; const y: Double; const width: Double; const height: Double; const url: TUri); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x**|Double|x coord\.|
|const|**y**|Double|y coord\.|
|const|**width**|Double|Width of the region\.|
|const|**height**|Double|Height of the region\.|
|const|**url**|TUri|Url where to navigate to\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)

# TPdfWriter\.Hyperlink\(Double, Double, Double, Double, Integer, Double, Double\)
Creates a local Hyperlink on the selected region to another page of the pdf document\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.Hyperlink(const x: Double; const y: Double; const width: Double; const height: Double; const pageDest: Integer; const xDest: Double; const yDest: Double); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**x**|Double|x coord\.|
|const|**y**|Double|y coord\.|
|const|**width**|Double|Width of the region\.|
|const|**height**|Double|Height of the region\.|
|const|**pageDest**|Integer|Page where the hyperlink will go\.|
|const|**xDest**|Double|X offset from the start of the page for the destination\.|
|const|**yDest**|Double|Y offset from the start of the page for the destination\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


---
uid: TPdfUsedFallbackFontError
description: TPdfUsedFallbackFontError
---

# TPdfUsedFallbackFontError Class

This class has information for a [TFlexCelError.PdfUsedFallbackFont](../TFlexCelError.md) error\. Look at [TFlexCelError.PdfUsedFallbackFont](../TFlexCelError.md) for more information\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TPdfUsedFallbackFontError = class(<a href="../TFlexCelErrorInfo/index.md">TFlexCelErrorInfo</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[OriginalFontName](OriginalFontName.md)|Font that should be used, but that doesn't contain the needed characters\.<br />|
|[SubstitutedFontName](SubstitutedFontName.md)|Fallback font that substituted [OriginalFontName](OriginalFontName.md)\.<br />|



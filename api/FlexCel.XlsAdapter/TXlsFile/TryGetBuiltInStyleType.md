---
uid: TXlsFile.TryGetBuiltInStyleType
description: TXlsFile.TryGetBuiltInStyleType
---

# TXlsFile\.TryGetBuiltInStyleType Method

Tries to convert a string into an built\-in style identifier\. Will return true if styleName can be converted, false otherwise\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.TryGetBuiltInStyleType(const styleName: string; out style: <a href="../../FlexCel.Core/TBuiltInStyle.md">TBuiltInStyle</a>; out level: Integer): Boolean; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**styleName**|string|Style that we want to convert to built\-in style\.|
|out|**style**|[TBuiltInStyle](../../FlexCel.Core/TBuiltInStyle.md)|Returns the built\-in style\. This value is only valid if this method returns true\.|
|out|**level**|Integer|Returns the level built\-in style \(1 based\)\. This value is only valid if this method returns true, and only applies to outline styles\. It will be 0 for non outline styles\.|


## Returns

True is styleNameis a built\-in style \(and thus style and level are valid\), false otherwise\.

## See also

* [TXlsFile](../TXlsFile/index.md)


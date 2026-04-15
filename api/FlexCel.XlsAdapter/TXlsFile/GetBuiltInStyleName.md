---
uid: TXlsFile.GetBuiltInStyleName
description: TXlsFile.GetBuiltInStyleName
---

# TXlsFile\.GetBuiltInStyleName Method

Returns the name for a built\-in style\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetBuiltInStyleName(const style: <a href="../../FlexCel.Core/TBuiltInStyle.md">TBuiltInStyle</a>; const level: Integer): string; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**style**|[TBuiltInStyle](../../FlexCel.Core/TBuiltInStyle.md)|Style you want find out the name\.|
|const|**level**|Integer|Used only if style is [TBuiltInStyle.RowLevel](../../FlexCel.Core/TBuiltInStyle.md) or [TBuiltInStyle.ColLevel](../../FlexCel.Core/TBuiltInStyle.md)\. It specifies the level of the outline, and must be a number between 1 and 7\. Keep it 0 for all other styles\.|


## Returns

The name for the Built in style\.

## See also

* [TXlsFile](../TXlsFile/index.md)


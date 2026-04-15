---
uid: TExcelFile.GetBuiltInStyleName
description: TExcelFile.GetBuiltInStyleName
---

# TExcelFile\.GetBuiltInStyleName Method

Returns the name for a built\-in style\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetBuiltInStyleName(const style: <a href="../TBuiltInStyle.md">TBuiltInStyle</a>; const level: Integer): string; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**style**|[TBuiltInStyle](../TBuiltInStyle.md)|Style you want find out the name\.|
|const|**level**|Integer|Used only if style is [TBuiltInStyle.RowLevel](../TBuiltInStyle.md) or [TBuiltInStyle.ColLevel](../TBuiltInStyle.md)\. It specifies the level of the outline, and must be a number between 1 and 7\. Keep it 0 for all other styles\.|


## Returns

The name for the Built in style\.

## See also

* [TExcelFile](../TExcelFile/index.md)


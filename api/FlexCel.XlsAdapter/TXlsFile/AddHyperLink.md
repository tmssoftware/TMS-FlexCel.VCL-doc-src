---
uid: TXlsFile.AddHyperLink
description: TXlsFile.AddHyperLink
---

# TXlsFile\.AddHyperLink Method

Adds a new hyperlink to the Active sheet\. Use [TExcelFile.SetHyperLink](../../FlexCel.Core/TExcelFile/SetHyperLink.md) to modify an existing one\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.AddHyperLink(const cellRange: <a href="../../FlexCel.Core/TXlsCellRange/index.md">TXlsCellRange</a>; const value: <a href="../../FlexCel.Core/THyperLink/index.md">THyperLink</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**cellRange**|[TXlsCellRange](../../FlexCel.Core/TXlsCellRange/index.md)|Range of cells the hyperlink will refer to\.|
|const|**value**|[THyperLink](../../FlexCel.Core/THyperLink/index.md)|Description of the hyperlink\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TXlsFile.SetStyle
description: TXlsFile.SetStyle
---

# TXlsFile\.SetStyle Method

Modifies an existing style if name already exists, or creates a new style if it doesn't\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetStyle(const name: string; const fmt: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name for the style\. It might be a user defined name, or a built\-in name\. You can get a list of built\-in names with [TExcelFile.GetBuiltInStyleName](../../FlexCel.Core/TExcelFile/GetBuiltInStyleName.md)|
|const|**fmt**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|The new style definition\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


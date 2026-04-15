---
uid: TExcelFile.SetStyle
description: TExcelFile.SetStyle
---

# TExcelFile\.SetStyle Method

Modifies an existing style if name already exists, or creates a new style if it doesn't\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetStyle(const name: string; const fmt: <a href="../TFlxFormat/index.md">TFlxFormat</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**name**|string|Name for the style\. It might be a user defined name, or a built\-in name\. You can get a list of built\-in names with [GetBuiltInStyleName](GetBuiltInStyleName.md)|
|const|**fmt**|[TFlxFormat](../TFlxFormat/index.md)|The new style definition\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


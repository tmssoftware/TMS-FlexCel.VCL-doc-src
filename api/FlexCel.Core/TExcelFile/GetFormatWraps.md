---
uid: TExcelFile.GetFormatWraps
description: TExcelFile.GetFormatWraps
---

# TExcelFile\.GetFormatWraps Method

Returns the if the cell can wrap\. Used to improve performance when we don't need the full format\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetFormatWraps(const row: Integer; const col: Integer; const testAlignment: <a href="../THFlxAlignment.md">THFlxAlignment</a>): Boolean; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**row**|Integer||
|const|**col**|Integer||
|const|**testAlignment**|[THFlxAlignment](../THFlxAlignment.md)|Alignment to be tested\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


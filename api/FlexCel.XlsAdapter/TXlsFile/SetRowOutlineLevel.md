---
uid: TXlsFile.SetRowOutlineLevel
description: TXlsFile.SetRowOutlineLevel
---

# TXlsFile\.SetRowOutlineLevel Method

Sets the Outline level for a row range\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetRowOutlineLevel(const firstRow: Integer; const lastRow: Integer; const level: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstRow**|Integer|Row index of the first row on the range\. \(1 based\)|
|const|**lastRow**|Integer|Row index of the last row on the range\. \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


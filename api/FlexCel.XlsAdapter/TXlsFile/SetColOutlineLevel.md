---
uid: TXlsFile.SetColOutlineLevel
description: TXlsFile.SetColOutlineLevel
---

# TXlsFile\.SetColOutlineLevel Method

Sets the Outline level for a column range\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetColOutlineLevel(const firstCol: Integer; const lastCol: Integer; const level: Integer); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**firstCol**|Integer|Column index of the first column on the range\. \(1 based\)|
|const|**lastCol**|Integer|Column index of the last column on the range\. \(1 based\)|
|const|**level**|Integer|Outline level\. must be between 0 and 7\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


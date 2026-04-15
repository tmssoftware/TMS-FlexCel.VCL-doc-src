---
uid: TXlsFile.SetFormat
description: TXlsFile.SetFormat
---

# TXlsFile\.SetFormat Method

Sets the font definition for a given format index\. Normally it is of not use, \(you should use AddFont or AddFormat instead\) but could be used to change the default format\. \(using SetFormat\(0, fmt\); \)\. This method will change style XFs and CellXfs, depending if aFormat  is a StyleXF or a CellXF\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetFormat(const formatIndex: Integer; const aFormat: <a href="../../FlexCel.Core/TFlxFormat/index.md">TFlxFormat</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**formatIndex**|Integer|Format index\. 0\-based|
|const|**aFormat**|[TFlxFormat](../../FlexCel.Core/TFlxFormat/index.md)|Format definition|


## See also

* [TXlsFile](../TXlsFile/index.md)


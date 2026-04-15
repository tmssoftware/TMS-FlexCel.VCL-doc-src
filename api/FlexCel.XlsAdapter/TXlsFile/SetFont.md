---
uid: TXlsFile.SetFont
description: TXlsFile.SetFont
---

# TXlsFile\.SetFont Method

Sets the font definition for a given font index\. Normally it is of not use, \(you should use AddFont or AddFormat instead\) but could be used to change the default font format\. \(using SetFont\(0, font\); \)

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetFont(const fontIndex: Integer; const aFont: <a href="../../FlexCel.Core/TFlxFont/index.md">TFlxFont</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fontIndex**|Integer|Font index\. 0\-based|
|const|**aFont**|[TFlxFont](../../FlexCel.Core/TFlxFont/index.md)|Font definition|


## See also

* [TXlsFile](../TXlsFile/index.md)


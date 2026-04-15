---
uid: TExcelFile.SetFont
description: TExcelFile.SetFont
---

# TExcelFile\.SetFont Method

Sets the font definition for a given font index\. Normally it is of not use, \(you should use AddFont or AddFormat instead\) but could be used to change the default font format\. \(using SetFont\(0, font\); \)

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetFont(const fontIndex: Integer; const aFont: <a href="../TFlxFont/index.md">TFlxFont</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**fontIndex**|Integer|Font index\. 0\-based|
|const|**aFont**|[TFlxFont](../TFlxFont/index.md)|Font definition|


## See also

* [TExcelFile](../TExcelFile/index.md)


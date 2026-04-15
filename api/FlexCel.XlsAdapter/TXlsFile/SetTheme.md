---
uid: TXlsFile.SetTheme
description: TXlsFile.SetTheme
---

# TXlsFile\.SetTheme Method

This is an advanced method, that allows you to set the full theme in use\. Normally you will just want to replace colors, and you can do this with [TExcelFile.SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](../../FlexCel.Core/TExcelFile/SetColorTheme.md#texcelfilesetcolorthemetprimarythemecolor-tdrawingcolor) and [TExcelFile.GetColorTheme\(TPrimaryThemeColor\)](../../FlexCel.Core/TExcelFile/GetColorTheme.md#texcelfilegetcolorthemetprimarythemecolor) methods\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetTheme(aTheme: <a href="../../FlexCel.Core/ITheme/index.md">ITheme</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aTheme**|[ITheme](../../FlexCel.Core/ITheme/index.md)|Theme to set\. You would normally use the result from [TExcelFile.GetTheme](../../FlexCel.Core/TExcelFile/GetTheme.md) here, or you might load a method from a "\.tmx" file\.<br />There are many standard tmx files available in an Office installation under the "Document Themes Version" folder|


## See also

* [TXlsFile](../TXlsFile/index.md)


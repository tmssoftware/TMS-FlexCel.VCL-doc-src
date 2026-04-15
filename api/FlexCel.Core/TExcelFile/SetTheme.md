---
uid: TExcelFile.SetTheme
description: TExcelFile.SetTheme
---

# TExcelFile\.SetTheme Method

This is an advanced method, that allows you to set the full theme in use\. Normally you will just want to replace colors, and you can do this with [SetColorTheme\(TPrimaryThemeColor, TDrawingColor\)](SetColorTheme.md#texcelfilesetcolorthemetprimarythemecolor-tdrawingcolor) and [GetColorTheme\(TPrimaryThemeColor\)](GetColorTheme.md#texcelfilegetcolorthemetprimarythemecolor) methods\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetTheme(aTheme: <a href="../ITheme/index.md">ITheme</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**aTheme**|[ITheme](../ITheme/index.md)|Theme to set\. You would normally use the result from [GetTheme](GetTheme.md) here, or you might load a method from a "\.tmx" file\.<br />There are many standard tmx files available in an Office installation under the "Document Themes Version" folder|


## See also

* [TExcelFile](../TExcelFile/index.md)


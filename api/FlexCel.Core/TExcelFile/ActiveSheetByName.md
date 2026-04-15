---
uid: TExcelFile.ActiveSheetByName
description: TExcelFile.ActiveSheetByName
---

# TExcelFile.ActiveSheetByName Property

The sheet where we are working on, referred by name instead of by index\.
To change the active sheet name, use [SheetName](SheetName.md)

## Remarks

Setting the active sheet will also set the selected sheet in the file, except when the object is a light clone \([LightClone](LightClone.md)\) For lightcloned object, the selected file won't change\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.ActiveSheetByName: string</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


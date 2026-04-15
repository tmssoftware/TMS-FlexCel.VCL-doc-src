---
uid: TXlsFile.ActiveSheetByName
description: TXlsFile.ActiveSheetByName
---

# TXlsFile.ActiveSheetByName Property

The sheet where we are working on, referred by name instead of by index\.
To change the active sheet name, use [TExcelFile.SheetName](../../FlexCel.Core/TExcelFile/SheetName.md)

## Remarks

Setting the active sheet will also set the selected sheet in the file, except when the object is a light clone \([TExcelFile.LightClone](../../FlexCel.Core/TExcelFile/LightClone.md)\) For lightcloned object, the selected file won't change\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.ActiveSheetByName: string</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


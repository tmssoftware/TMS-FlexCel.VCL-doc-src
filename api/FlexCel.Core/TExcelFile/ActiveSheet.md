---
uid: TExcelFile.ActiveSheet
description: TExcelFile.ActiveSheet
---

# TExcelFile.ActiveSheet Property

The Sheet where we are working on, 1\-based\(First sheet is 1, not 0\)\.
Always set this property before working on a file\.
You can read or write this value\.


## Remarks

Setting the active sheet will also set the selected sheet in the file, except when the object is a light clone \([LightClone](LightClone.md)\) For lightcloned object, the selected file won't change\.
Also if the file has multiple windows, this property will only change the selected sheet for the first window\.
Use [ActiveSheetForActiveWindow](ActiveSheetForActiveWindow.md) if you want to change the active sheet for a different window\.

Finally, remember that a file can have more than one sheet selected, even if only one can be active\.
To Select mutiple sheets, call [SetSheetSelected](SetSheetSelected.md)\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.ActiveSheet: Integer</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TExcelFile.ActiveSheetForActiveWindow
description: TExcelFile.ActiveSheetForActiveWindow
---

# TExcelFile.ActiveSheetForActiveWindow Property

Gets or sets the active sheet for the [ActiveWindow](ActiveWindow.md)\. Note that this won't change the active sheet for FlexCel when you enter a value, you still need to call [ActiveSheet](ActiveSheet.md) for that\.
This property will only change the sheet that is active in that window when you open the file in Excel\.
Setting this property will also unselect the other sheets\. If you want to select multiple sheets, make sure to select them \*after\* setting the ActiveSheetForActiveWindow\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.ActiveSheetForActiveWindow: Integer</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


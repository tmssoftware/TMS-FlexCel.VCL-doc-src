---
uid: TXlsFile.ActiveSheetForActiveWindow
description: TXlsFile.ActiveSheetForActiveWindow
---

# TXlsFile.ActiveSheetForActiveWindow Property

Gets or sets the active sheet for the [TExcelFile.ActiveWindow](../../FlexCel.Core/TExcelFile/ActiveWindow.md)\. Note that this won't change the active sheet for FlexCel when you enter a value, you still need to call [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) for that\.
This property will only change the sheet that is active in that window when you open the file in Excel\.
Setting this property will also unselect the other sheets\. If you want to select multiple sheets, make sure to select them \*after\* setting the ActiveSheetForActiveWindow\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.ActiveSheetForActiveWindow: Integer</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


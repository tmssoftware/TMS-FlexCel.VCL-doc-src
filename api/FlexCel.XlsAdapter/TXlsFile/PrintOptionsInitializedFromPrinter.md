---
uid: TXlsFile.PrintOptionsInitializedFromPrinter
description: TXlsFile.PrintOptionsInitializedFromPrinter
---

# TXlsFile.PrintOptionsInitializedFromPrinter Property

If this property is false, then Excel has not read the printer options from the printer, and [TExcelFile.PrintLandscape](../../FlexCel.Core/TExcelFile/PrintLandscape.md), [TExcelFile.PrintPaperSize](../../FlexCel.Core/TExcelFile/PrintPaperSize.md), [TExcelFile.PrintScale](../../FlexCel.Core/TExcelFile/PrintScale.md), [TExcelFile.PrintXResolution](../../FlexCel.Core/TExcelFile/PrintXResolution.md), [TExcelFile.PrintYResolution](../../FlexCel.Core/TExcelFile/PrintYResolution.md) and [TExcelFile.PrintCopies](../../FlexCel.Core/TExcelFile/PrintCopies.md) will be ignored\. This property will change automatically to true if you manually change any of the above properties\.


## Remarks

You shouldn't have to set this property, as it is set automatically to true when you set the others like [TExcelFile.PrintLandscape](../../FlexCel.Core/TExcelFile/PrintLandscape.md)\. But if you set it to true, it will not only set the print options to initialized, but also initialize all uninitialized properties like [TExcelFile.PrintLandscape](../../FlexCel.Core/TExcelFile/PrintLandscape.md) to default values\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.PrintOptionsInitializedFromPrinter: Boolean</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


---
uid: TExcelFile.PrintOptionsInitializedFromPrinter
description: TExcelFile.PrintOptionsInitializedFromPrinter
---

# TExcelFile.PrintOptionsInitializedFromPrinter Property

If this property is false, then Excel has not read the printer options from the printer, and [PrintLandscape](PrintLandscape.md), [PrintPaperSize](PrintPaperSize.md), [PrintScale](PrintScale.md), [PrintXResolution](PrintXResolution.md), [PrintYResolution](PrintYResolution.md) and [PrintCopies](PrintCopies.md) will be ignored\. This property will change automatically to true if you manually change any of the above properties\.


## Remarks

You shouldn't have to set this property, as it is set automatically to true when you set the others like [PrintLandscape](PrintLandscape.md)\. But if you set it to true, it will not only set the print options to initialized, but also initialize all uninitialized properties like [PrintLandscape](PrintLandscape.md) to default values\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TExcelFile/index.md">TExcelFile</a>.PrintOptionsInitializedFromPrinter: Boolean</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


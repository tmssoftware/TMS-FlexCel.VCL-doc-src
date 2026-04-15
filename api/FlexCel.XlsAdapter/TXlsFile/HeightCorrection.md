---
uid: TXlsFile.HeightCorrection
description: TXlsFile.HeightCorrection
---

# TXlsFile.HeightCorrection Property

Factor to multiply default row heights\. See remarks for a detailed explanation\.


## Remarks

Excel does not print the same things to all printers \(or even the same printer with another resolution\)\.
Depending on the driver and resolution, printed columns and rows will be a little smaller or bigger\.




FlexCel uses \.NET framework to print, and so it is resolution independent, it will always print the same no matter where\. So FlexCel is tuned to print like Excel on a 600 dpi generic printer\.
This will probably be ok for most uses, but in some cases might cause FlexCel to print an Extra page with only one column or row\.




You can use this property and [TExcelFile.WidthCorrection](../../FlexCel.Core/TExcelFile/WidthCorrection.md) to manually fine tune FlexCel printing, previewing and exporting to PDF to make it smaller or larger\. A normal value for this property might be 1\.05 or 0\.99, but don't use it unless you really need to\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TXlsFile/index.md">TXlsFile</a>.HeightCorrection: Double</code></pre>

## Examples

To calculate the exact HeightCorrection and WidthCorrection for your printer create a new Excel sheet, make column A wide \(almost a sheet wide\) and row 1 larger \(almost a sheet tall\)\.
Set the borders around cell A1 to a solid line\.
Now, print this file from Excel and from FlexCel \(you can use the PrintPreview demo for this\) and compare the 2 resulting boxes\. If for example the Excel printed box is 1\.2 cm wide and FlexCel is 1\.4,  WidthCorrection should be 1\.4/1\.2\.  \(A larger WidthCorrection means a smaller box\)

## See also

* [TXlsFile](../TXlsFile/index.md)


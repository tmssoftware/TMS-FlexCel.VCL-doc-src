---
uid: TExcelFile.GetPrinterDriverSettings
description: TExcelFile.GetPrinterDriverSettings
---

# TExcelFile\.GetPrinterDriverSettings Method

Returns printer driver settings\. This method is not intended to be used alone, but together with [SetPrinterDriverSettings](SetPrinterDriverSettings.md) to copy printer driver information from a file to another\.


## Remarks

Excel stores printer settings in **two places**
1. Standard printer settings: You can set/read this with [PrintPaperSize](PrintPaperSize.md),  [PrintScale](PrintScale.md), [PrintLandscape](PrintLandscape.md), [PrintXResolution](PrintXResolution.md), [PrintYResolution](PrintYResolution.md) and [PrintCopies](PrintCopies.md)
2. Printer driver settings: You can access this with GetPrinterDriverSettings and SetPrinterDriverSettings\.<br />

**NOTE THAT THOSE PLACES STORE DUPLICATED INFORMATION\.**  For example, Excel stores the PageSize on both *Standard printer settings* and *Printer driver settings\.*



Always that a value is stored on both places, *\(1\) Standard printer settings* takes preference\.




If you set PaperSize = A4 on standard settings and PaperSize = A5 on driver settings, A4 will be used\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetPrinterDriverSettings: <a href="../TPrinterDriverSettings/index.md">TPrinterDriverSettings</a>; virtual; abstract;</code></pre>

## Examples

To copy the printer driver information from an empty template to the working file, use:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xlsWorkingCopy.SetPrinterDriverSettings(xlsTemplate.GetPrinterDriverSettings);</span></span>
<span class="line"></span></code></pre>

If you have defined a printer specific paper size, and you want to use it, you should call

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span style="color:#000000;--shiki-dark:#D4D4D4">  xlsWorkingCopy.PrintPaperSize := xlsTemplate.PrintPaperSize;</span></span>
<span class="line"></span></code></pre>

after copying the driver settings\.


## See also

* [TExcelFile](../TExcelFile/index.md)


---
uid: TXlsFile.LightClone
description: TXlsFile.LightClone
---

# TXlsFile\.LightClone Method

Returns a copy of this ExcelFile object with the same backing data, so the cells in both objects are the same\.
Using a light clone allows you to read from a single ExcelFile in two different threads, since while the data is the same \(so you don't use twice the memory as a real clone would\), you can have separate activesheets in both\. So one thread can be reading from the "original" file with ActiveSheet = 1, and the other thread could be reading from the light clone with activeSheet = 3\.

**Important**: This object MUST be freed before the parent object is freed\.


## Remarks

There is a difference between a light clone and the original object\. When you set the [TExcelFile.ActiveSheet](../../FlexCel.Core/TExcelFile/ActiveSheet.md) in the clone, it won't actually set the selected sheet in the physical file as setting it in the original will do\. This is because the light clone is targeted at reading, and you don't want to change the actual file you are reading\. While FlexCel is safe for more than one thread reading from the same object, it isn't for more than one thread writing to the same object\. When modifying an XlsFile, you shouldn't use light clones, use them only for reading\.

You can see if an object is a light clone or not by looking at the [TExcelFile.IsLightClone](../../FlexCel.Core/TExcelFile/IsLightClone.md) property\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.LightClone: <a href="../../FlexCel.Core/TExcelFile/index.md">TExcelFile</a>; override;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


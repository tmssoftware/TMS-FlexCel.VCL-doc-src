---
uid: TXlsFile.GetXmlMap
description: TXlsFile.GetXmlMap
---

# TXlsFile\.GetXmlMap Method

Returns the XML Maps in the file if it has any, or null if there are no XML Maps\. Note that the map returned  is a copy, so modifying it won't modify the map in the file\. To modify the map in the file you need to get it with [TExcelFile.GetXmlMap](../../FlexCel.Core/TExcelFile/GetXmlMap.md), modify it, then set it with [TExcelFile.SetXmlMap](../../FlexCel.Core/TExcelFile/SetXmlMap.md)

## Remarks

This method only works for xlsx/m files, not for xls\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TXlsFile/index.md">TXlsFile</a>.GetXmlMap: <a href="../../FlexCel.Core/IXmlMap/index.md">IXmlMap</a>; override;</code></pre>

## See also

* [TXlsFile](../TXlsFile/index.md)


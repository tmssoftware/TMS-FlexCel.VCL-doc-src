---
uid: TExcelFile.GetXmlMap
description: TExcelFile.GetXmlMap
---

# TExcelFile\.GetXmlMap Method

Returns the XML Maps in the file if it has any, or null if there are no XML Maps\. Note that the map returned  is a copy, so modifying it won't modify the map in the file\. To modify the map in the file you need to get it with [GetXmlMap](GetXmlMap.md), modify it, then set it with [SetXmlMap](SetXmlMap.md)

## Remarks

This method only works for xlsx/m files, not for xls\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TExcelFile/index.md">TExcelFile</a>.GetXmlMap: <a href="../IXmlMap/index.md">IXmlMap</a>; virtual; abstract;</code></pre>

## See also

* [TExcelFile](../TExcelFile/index.md)


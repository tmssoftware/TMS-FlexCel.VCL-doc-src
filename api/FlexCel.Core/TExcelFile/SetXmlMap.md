---
uid: TExcelFile.SetXmlMap
description: TExcelFile.SetXmlMap
---

# TExcelFile\.SetXmlMap Method

Sets the XML Maps in the file\. This is equivalent to going to the "Developer" tab in Excel and then clicking in  Source in the XML section\.

Set it to null to remove the XML Maps in the file\.


## Remarks

This method only works for xlsx/m files, not for xls\.

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.SetXmlMap(map: <a href="../IXmlMap/index.md">IXmlMap</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**map**|[IXmlMap](../IXmlMap/index.md)|Map that we wish to set\. Make it null to remove the maps in the file\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


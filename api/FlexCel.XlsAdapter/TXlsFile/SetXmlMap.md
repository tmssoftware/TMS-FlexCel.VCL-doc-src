---
uid: TXlsFile.SetXmlMap
description: TXlsFile.SetXmlMap
---

# TXlsFile\.SetXmlMap Method

Sets the XML Maps in the file\. This is equivalent to going to the "Developer" tab in Excel and then clicking in  Source in the XML section\.

Set it to null to remove the XML Maps in the file\.


## Remarks

This method only works for xlsx/m files, not for xls\.

## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsFile/index.md">TXlsFile</a>.SetXmlMap(map: <a href="../../FlexCel.Core/IXmlMap/index.md">IXmlMap</a>); override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
||**map**|[IXmlMap](../../FlexCel.Core/IXmlMap/index.md)|Map that we wish to set\. Make it null to remove the maps in the file\.|


## See also

* [TXlsFile](../TXlsFile/index.md)


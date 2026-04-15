---
uid: TXlsChart.SetObjectText
description: TXlsChart.SetObjectText
---

# TXlsChart\.SetObjectText Method

## Overloads

* [TXlsChart\.SetObjectText\(Integer, string, string\)](#txlschartsetobjecttextinteger-string-string)
* [TXlsChart\.SetObjectText\(Integer, string, TRichString\)](#txlschartsetobjecttextinteger-string-trichstring)
* [TXlsChart\.SetObjectText\(Integer, string, TDrawingRichString\)](#txlschartsetobjecttextinteger-string-tdrawingrichstring)

# TXlsChart\.SetObjectText\(Integer, string, string\)
Sets the text for an autoshape\. If the object does not accept text, this method will do nothing\.
This version of the method will only modify the text of the object, and preserve the existing formatting in the object if there was one\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: string); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TXlsBaseChart.GetObjectProperties](../TXlsBaseChart/GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|string|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

# TXlsChart\.SetObjectText\(Integer, string, TRichString\)
Sets the text for an autoshape\. If the object does not accept text, this method will do nothing\.
This version of the method will only modify the rich string properties of the object text, and preserve those things not available in a TRichString like wordArt effects\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TXlsBaseChart.GetObjectProperties](../TXlsBaseChart/GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsChart](../TXlsChart/index.md)

# TXlsChart\.SetObjectText\(Integer, string, TDrawingRichString\)
Changes the text inside an object of the chart\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsChart/index.md">TXlsChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../../FlexCel.Core/TDrawingRichString/index.md">TDrawingRichString</a>); overload; override;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object, between 1 and ObjectCount />|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [TXlsBaseChart.GetObjectProperties](../TXlsBaseChart/GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|[TDrawingRichString](../../FlexCel.Core/TDrawingRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsChart](../TXlsChart/index.md)


---
uid: TXlsBaseChart.SetObjectText
description: TXlsBaseChart.SetObjectText
---

# TXlsBaseChart\.SetObjectText Method

## Overloads

* [TXlsBaseChart\.SetObjectText\(Integer, string, string\)](#txlsbasechartsetobjecttextinteger-string-string)
* [TXlsBaseChart\.SetObjectText\(Integer, string, TRichString\)](#txlsbasechartsetobjecttextinteger-string-trichstring)
* [TXlsBaseChart\.SetObjectText\(Integer, string, TDrawingRichString\)](#txlsbasechartsetobjecttextinteger-string-tdrawingrichstring)

# TXlsBaseChart\.SetObjectText\(Integer, string, string\)
Sets the text for an autoshape\. If the object does not accept text, this method will do nothing\.
This version of the method will only modify the text of the object, and preserve the existing formatting in the object if there was one\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|string|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.SetObjectText\(Integer, string, TRichString\)
Sets the text for an autoshape\. If the object does not accept text, this method will do nothing\.
This version of the method will only modify the rich string properties of the object text, and preserve those things not available in a TRichString like wordArt effects\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../../FlexCel.Core/TRichString/index.md">TRichString</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object \(1\-based\)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|[TRichString](../../FlexCel.Core/TRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)

# TXlsBaseChart\.SetObjectText\(Integer, string, TDrawingRichString\)
Changes the text inside an object of the chart\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TXlsBaseChart/index.md">TXlsBaseChart</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../../FlexCel.Core/TDrawingRichString/index.md">TDrawingRichString</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object, between 1 and ObjectCount />|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute"\(it starts with "\\\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\\\1\\\\2\\\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\\\3"|
|const|**text**|[TDrawingRichString](../../FlexCel.Core/TDrawingRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [TXlsBaseChart](../TXlsBaseChart/index.md)


---
uid: IEmbeddedObjects.SetObjectText
description: IEmbeddedObjects.SetObjectText
---

# IEmbeddedObjects\.SetObjectText Method

## Overloads

* [IEmbeddedObjects\.SetObjectText\(Integer, string, string\)](#iembeddedobjectssetobjecttextinteger-string-string)
* [IEmbeddedObjects\.SetObjectText\(Integer, string, TRichString\)](#iembeddedobjectssetobjecttextinteger-string-trichstring)
* [IEmbeddedObjects\.SetObjectText\(Integer, string, TDrawingRichString\)](#iembeddedobjectssetobjecttextinteger-string-tdrawingrichstring)

# IEmbeddedObjects\.SetObjectText\(Integer, string, string\)
Changes the text inside an object of this object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: string); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object, between 1 and [ObjectCount](ObjectCount.md)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute" \(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**text**|string|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [IEmbeddedObjects](../IEmbeddedObjects/index.md)

# IEmbeddedObjects\.SetObjectText\(Integer, string, TRichString\)
Changes the text inside an object of this object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../TRichString/index.md">TRichString</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object, between 1 and [ObjectCount](ObjectCount.md)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute" \(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**text**|[TRichString](../TRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [IEmbeddedObjects](../IEmbeddedObjects/index.md)

# IEmbeddedObjects\.SetObjectText\(Integer, string, TDrawingRichString\)
Changes the text inside an object of this object\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IEmbeddedObjects/index.md">IEmbeddedObjects</a>.SetObjectText(const objectIndex: Integer; const objectPath: string; const text: <a href="../TDrawingRichString/index.md">TDrawingRichString</a>); overload; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**objectIndex**|Integer|Index of the object, between 1 and [ObjectCount](ObjectCount.md)|
|const|**objectPath**|string|Index to the child object you want to change the text\.<br />If it is a simple object, you can use String\.Empty here, if not you need to get the ObjectPath from [GetObjectProperties](GetObjectProperties.md)<br />If it is "absolute" \(it starts with "\\"\), then the path includes the objectIndex, and the objectIndex is not used\. An object path of "\\1\\2\\3" is exactly the same as using objectIndex = 1 and objectPath = "2\\3"|
|const|**text**|[TDrawingRichString](../TDrawingRichString/index.md)|Text you want to use\. Use null to delete text from an AutoShape\.|


## See also

* [IEmbeddedObjects](../IEmbeddedObjects/index.md)


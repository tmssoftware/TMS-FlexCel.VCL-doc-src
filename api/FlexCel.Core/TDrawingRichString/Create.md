---
uid: TDrawingRichString.Create
description: TDrawingRichString.Create
---

# TDrawingRichString\.Create Method

## Overloads

* [TDrawingRichString\.Create](#tdrawingrichstringcreate)
* [TDrawingRichString\.Create\(string\)](#tdrawingrichstringcreatestring)
* [TDrawingRichString\.Create\(TDrawingTextParagraphArray\)](#tdrawingrichstringcreatetdrawingtextparagrapharray)
* [TDrawingRichString\.Create\(string, TDrawingAlignment\)](#tdrawingrichstringcreatestring-tdrawingalignment)

# TDrawingRichString\.Create
Creates a new TDrawingRichString with a null value\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.Create: <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.Create\(string\)
Creates a new TDrawingRichString with no formatting and left alignment\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.Create(const s: string): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String with the data\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.Create\(TDrawingTextParagraphArray\)
Creates a new TDrawingRichString from an array of paragraphs\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.Create(const aParagraphs: <a href="../TDrawingTextParagraph/index.md">TArray&lt;TDrawingTextParagraph></a>): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aParagraphs**|[TArray\<&#8203;TDrawing&#8203;Text&#8203;Paragraph>](../TDrawingTextParagraph/index.md)|Array of RTF runs with the data and formatting for the string\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.Create\(string, TDrawingAlignment\)
Creates a new TDrawingRichString with no formatting and the specified alignment\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.Create(const s: string; const hAlign: <a href="../TDrawingAlignment.md">TDrawingAlignment</a>): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string|String with the data\.|
|const|**hAlign**|[TDrawingAlignment](../TDrawingAlignment.md)|Alignment for the text\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)


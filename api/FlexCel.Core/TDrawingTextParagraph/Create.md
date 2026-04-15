---
uid: TDrawingTextParagraph.Create
description: TDrawingTextParagraph.Create
---

# TDrawingTextParagraph\.Create Method

## Overloads

* [TDrawingTextParagraph\.Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties\)](#tdrawingtextparagraphcreatetdrawingtextrunarray-tdrawingparagraphproperties-tdrawingtextproperties)
* [TDrawingTextParagraph\.Create\(string, TDrawingParagraphProperties, TDrawingTextProperties\)](#tdrawingtextparagraphcreatestring-tdrawingparagraphproperties-tdrawingtextproperties)
* [TDrawingTextParagraph\.Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties, string\)](#tdrawingtextparagraphcreatetdrawingtextrunarray-tdrawingparagraphproperties-tdrawingtextproperties-string)

# TDrawingTextParagraph\.Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties\)
Creates a new TDrawingTextParagraph\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>.Create(const aRuns: <a href="../TDrawingTextRun/index.md">TArray&lt;TDrawingTextRun></a>; const aProperties: <a href="../TDrawingParagraphProperties/index.md">TDrawingParagraphProperties</a>; const aEndParagraphProperties: <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>): <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRuns**|[TArray\<&#8203;TDrawing&#8203;Text&#8203;Run>](../TDrawingTextRun/index.md)||
|const|**aProperties**|[TDrawingParagraph&#8203;Properties](../TDrawingParagraphProperties/index.md)||
|const|**aEndParagraphProperties**|[TDrawingText&#8203;Properties](../TDrawingTextProperties/index.md)||


## See also

* [TDrawingTextParagraph](../TDrawingTextParagraph/index.md)

# TDrawingTextParagraph\.Create\(string, TDrawingParagraphProperties, TDrawingTextProperties\)
Creates a new TDrawingTextParagraph based on a simple string\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>.Create(const s: string; const aProperties: <a href="../TDrawingParagraphProperties/index.md">TDrawingParagraphProperties</a>; const aEndParagraphProperties: <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>): <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**s**|string||
|const|**aProperties**|[TDrawingParagraph&#8203;Properties](../TDrawingParagraphProperties/index.md)||
|const|**aEndParagraphProperties**|[TDrawingText&#8203;Properties](../TDrawingTextProperties/index.md)||


## See also

* [TDrawingTextParagraph](../TDrawingTextParagraph/index.md)

# TDrawingTextParagraph\.Create\(TDrawingTextRunArray, TDrawingParagraphProperties, TDrawingTextProperties, string\)
Creates a new TDrawingTextParagraph instance\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>.Create(const aRuns: <a href="../TDrawingTextRun/index.md">TArray&lt;TDrawingTextRun></a>; const aProperties: <a href="../TDrawingParagraphProperties/index.md">TDrawingParagraphProperties</a>; const aEndParagraphProperties: <a href="../TDrawingTextProperties/index.md">TDrawingTextProperties</a>; const aUnknownXml: string): <a href="../TDrawingTextParagraph/index.md">TDrawingTextParagraph</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aRuns**|[TArray\<&#8203;TDrawing&#8203;Text&#8203;Run>](../TDrawingTextRun/index.md)||
|const|**aProperties**|[TDrawingParagraph&#8203;Properties](../TDrawingParagraphProperties/index.md)||
|const|**aEndParagraphProperties**|[TDrawingText&#8203;Properties](../TDrawingTextProperties/index.md)||
|const|**aUnknownXml**|string||


## See also

* [TDrawingTextParagraph](../TDrawingTextParagraph/index.md)


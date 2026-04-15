---
uid: TDrawingRichString.FromRichString
description: TDrawingRichString.FromRichString
---

# TDrawingRichString\.FromRichString Method

## Overloads

* [TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingAlignment\)](#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingalignment)
* [TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment\)](#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingrichstring-tdrawingalignment)
* [TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment, Boolean\)](#tdrawingrichstringfromrichstringtrichstring-tcoreexcelfile-tdrawingrichstring-tdrawingalignment-boolean)

# TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingAlignment\)
Returns a new TDrawingRichString from a TRichString\. Note that the conversion is not perfect since information in both kind of strings is different\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.FromRichString(const aValue: <a href="../TRichString/index.md">TRichString</a>; const xls: TCoreExcelFile; const HAlign: <a href="../TDrawingAlignment.md">TDrawingAlignment</a>): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|[TRichString](../TRichString/index.md)|String that we want to convert\.|
|const|**xls**|TCoreExcelFile|Excel file with the string\. It will be used to convert indexed colors if there are any\.|
|const|**HAlign**|[TDrawingAlignment](../TDrawingAlignment.md)|Alignment for the paragraphs\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment\)
Returns a new TDrawingRichString from a TRichString\. Note that the conversion is not perfect since information in both kind of strings is different\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.FromRichString(const aValue: <a href="../TRichString/index.md">TRichString</a>; const xls: TCoreExcelFile; const origString: <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; const HAlign: <a href="../TDrawingAlignment.md">TDrawingAlignment</a>): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|[TRichString](../TRichString/index.md)|String that we want to convert\.|
|const|**xls**|TCoreExcelFile|Excel file with the string\. It will be used to convert indexed colors if there are any\.|
|const|**origString**|[TDrawingRichString](../TDrawingRichString/index.md)|String used as a template when replacing text\.|
|const|**HAlign**|[TDrawingAlignment](../TDrawingAlignment.md)|Alignment for the paragraphs\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)

# TDrawingRichString\.FromRichString\(TRichString, TCoreExcelFile, TDrawingRichString, TDrawingAlignment, Boolean\)
Returns a new TDrawingRichString from a TRichString\. Note that the conversion is not perfect since information in both kind of strings is different\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TDrawingRichString/index.md">TDrawingRichString</a>.FromRichString(const aValue: <a href="../TRichString/index.md">TRichString</a>; const xls: TCoreExcelFile; const origString: <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; const HAlign: <a href="../TDrawingAlignment.md">TDrawingAlignment</a>; const splitIntoParagraphs: Boolean): <a href="../TDrawingRichString/index.md">TDrawingRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|[TRichString](../TRichString/index.md)|String that we want to convert\.|
|const|**xls**|TCoreExcelFile|Excel file with the string\. It will be used to convert indexed colors if there are any\.|
|const|**origString**|[TDrawingRichString](../TDrawingRichString/index.md)|String used as a template when replacing text\.|
|const|**HAlign**|[TDrawingAlignment](../TDrawingAlignment.md)|Alignment for the paragraphs\.|
|const|**splitIntoParagraphs**|Boolean|You will normally want this parameter to be true\. If false, returns in the text will be encoded in the same paragraph\.<br />This is needed in some parts in the xlsx file, but normally you want one paragraph per line\.|


## See also

* [TDrawingRichString](../TDrawingRichString/index.md)


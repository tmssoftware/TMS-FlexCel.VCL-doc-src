---
uid: TRichString.Create
description: TRichString.Create
---

# TRichString\.Create Method

## Overloads

* [TRichString\.Create](#trichstringcreate)
* [TRichString\.Create\(string\)](#trichstringcreatestring)
* [TRichString\.Create\(string, TRTFRunArray\)](#trichstringcreatestring-trtfrunarray)
* [TRichString\.Create\(string, TFList\<TRTFRun>\)](#trichstringcreatestring-tflisttrtfrun)
* [TRichString\.Create\(string, TBytes, TCoreExcelFile\)](#trichstringcreatestring-tbytes-tcoreexcelfile)
* [TRichString\.Create\(string, TRichString, Integer\)](#trichstringcreatestring-trichstring-integer)

# TRichString\.Create
Constructs an empty RichString\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create: <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Create\(string\)
Constructs a RichString without formatting\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create(const aValue: string): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|string||


## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Create\(string, TRTFRunArray\)
Constructs a default RichString with text and RTF info\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create(const aValue: string; const aRTFRuns: <a href="../TRTFRun/index.md">TArray&lt;TRTFRun></a>): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|string|Cell Text|
|const|**aRTFRuns**|[TArray\<TRTFRun>](../TRTFRun/index.md)|Array of TRTFRuns structs\. This value will be COPIED, so old reference is not used|


## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Create\(string, TFList\<TRTFRun>\)
Constructs a RichString with text and RTF info, using an RTF ArrayList\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create(const aValue: string; const RTFRuns: TFList&lt;<a href="../TRTFRun/index.md">TRTFRun</a>&gt;): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|string|Cell Text|
|const|**RTFRuns**|TFList\<[TRTFRun](../TRTFRun/index.md)>|ArrayList with RTFRuns\.|


## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Create\(string, TBytes, TCoreExcelFile\)
Constructs a default RichString with text and RTF info\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create(const aValue: string; const aRTFRuns: TBytes; const aFontList: TCoreExcelFile): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|string|Cell text\.|
|const|**aRTFRuns**|TBytes|Rich text info|
|const|**aFontList**|TCoreExcelFile|List with the fonts to convert\.|


## See also

* [TRichString](../TRichString/index.md)

# TRichString\.Create\(string, TRichString, Integer\)
Constructs a default RichString with text and RTF info\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TRichString/index.md">TRichString</a>.Create(const aValue: string; const aRichString: <a href="../TRichString/index.md">TRichString</a>; const offset: Integer): <a href="../TRichString/index.md">TRichString</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aValue**|string|Cell Text|
|const|**aRichString**|[TRichString](../TRichString/index.md)|Rich string with the RTF values to copy\. This value will be COPIED, so old reference is not used|
|const|**offset**|Integer|How many characters the RTFRun must be moved\. For example: RichString\(s\.SubString\(3\), RTFRuns, 3\) will adapt the RTFRun for s to the new substring\.|


## See also

* [TRichString](../TRichString/index.md)


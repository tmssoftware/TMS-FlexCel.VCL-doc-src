---
uid: TPdfProperties.Create
description: TPdfProperties.Create
---

# TPdfProperties\.Create Method

## Overloads

* [TPdfProperties\.Create](#tpdfpropertiescreate)
* [TPdfProperties\.Create\(string, string, string, string, string\)](#tpdfpropertiescreatestring-string-string-string-string)
* [TPdfProperties\.Create\(string, string, string, string, string, string\)](#tpdfpropertiescreatestring-string-string-string-string-string)

# TPdfProperties\.Create
Creates a new instance of the class\. All properties are set to empty\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfProperties/index.md">TPdfProperties</a>.Create: <a href="../TPdfProperties/index.md">TPdfProperties</a>; static; overload;</code></pre>

## See also

* [TPdfProperties](../TPdfProperties/index.md)

# TPdfProperties\.Create\(string, string, string, string, string\)
Creates a new instance of the class with given properties\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfProperties/index.md">TPdfProperties</a>.Create(const aTitle: string; const aAuthor: string; const aSubject: string; const aKeywords: string; const aCreator: string): <a href="../TPdfProperties/index.md">TPdfProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTitle**|string|Document title\.|
|const|**aAuthor**|string|Document author\.|
|const|**aSubject**|string|Document subject\.|
|const|**aKeywords**|string|Keywords to search on the document\.|
|const|**aCreator**|string|Application that created the document\.|


## See also

* [TPdfProperties](../TPdfProperties/index.md)

# TPdfProperties\.Create\(string, string, string, string, string, string\)
Creates a new instance of the class with given properties\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TPdfProperties/index.md">TPdfProperties</a>.Create(const aTitle: string; const aAuthor: string; const aSubject: string; const aKeywords: string; const aCreator: string; const aLanguage: string): <a href="../TPdfProperties/index.md">TPdfProperties</a>; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aTitle**|string|Document title\.|
|const|**aAuthor**|string|Document author\.|
|const|**aSubject**|string|Document subject\.|
|const|**aKeywords**|string|Keywords to search on the document\.|
|const|**aCreator**|string|Application that created the document\.|
|const|**aLanguage**|string|Language identifier specifying the natural language for the document\. This should be a standard specifier like "en\-US"\.<br /><br />Note that the language will be used by text\-to\-speech engines to read text out loud, so it is recommended to set this property\.|


## See also

* [TPdfProperties](../TPdfProperties/index.md)


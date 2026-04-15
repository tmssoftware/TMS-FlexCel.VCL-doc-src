---
uid: TPdfProperties
description: TPdfProperties
---

# TPdfProperties Record

Encapsulates the document properties for the PDF file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfProperties = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Title](Title.md)|Document title\.<br />|
|[Author](Author.md)|Document author\.<br />|
|[Subject](Subject.md)|Document subject\.<br />|
|[Keywords](Keywords.md)|Keywords to search on the document\.<br />|
|[Creator](Creator.md)|Application that created the document\.<br />|
|[Language](Language.md)|Language identifier specifying the natural language for the document\. This should be a standard specifier like "en\-US"\.<br /><br />Note that the language will be used by text\-to\-speech engines to read text out loud, so it is recommended to set this property\.<br /><br />You can see a list of languages here: http:&#8203;//&#8203;msdn\.&#8203;microsoft\.&#8203;com/&#8203;en\-&#8203;us/&#8203;library/&#8203;ee825488\(&#8203;v=&#8203;cs\.&#8203;20\)&#8203;\.&#8203;aspx|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tpdfpropertiescreate)<br />  [Create\(string, string, string, string, string\)](Create.md#tpdfpropertiescreatestring-string-string-string-string)<br />  [Create\(string, string, string, string, string, string\)](Create.md#tpdfpropertiescreatestring-string-string-string-string-string)<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|



---
uid: ITokenList
description: ITokenList
---

# ITokenList Interface

A list of tokens which create a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">ITokenList = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Add](Add.md)|Adds a new token to the end of the list\.<br />|
|[Clear](Clear.md)|Removes all tokens from the list\.<br />|
|[Insert](Insert.md)|Inserts a specific token into the list at a given position \(0 based\)\.<br />|
|[RemoveAt](RemoveAt.md)|Removes the token at index\.<br />|
|[GetEnumerator](GetEnumerator.md)|Returns the enumerator for the class\.<br />|


## Properties

|Name|Description|
|---|---|
|[Count](Count.md)|The number of tokens in the list\.<br />|
|[Item\[const index\]](Itemconst-index.md)|Gets or sets the token at the given index\.<br />|
|[IsArrayFormula](IsArrayFormula.md)|If true, the tokens in this list refer to an array formula\.<br />|
|[Span](Span.md)|This property only applies if [IsArrayFormula](IsArrayFormula.md) is true\. It has the range for the array formula\.<br />|



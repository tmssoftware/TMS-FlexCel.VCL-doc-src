---
uid: TFormulaMessages
description: TFormulaMessages
---

# TFormulaMessages Record

Tokens that can be used on a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFormulaMessages = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[ErrString](ErrString.md)|Message for the ErrorCode\.<br />|
|[TokenString](TokenString.md)|Formula tokens\.<br />|
|[TokenChar](TokenChar.md)|Returns the formula token as a character\.<br />|
|[FloatToString](FloatToString.md)|This is a non\-localized version of FloatToStr It will always use "\." as decimal separator\.<br />If you are localizing this unit to your language, change this function to be: public string FloatToString\(&#8203;double Value\) \{ return Value\.ToString\(\); \} And it will use your current locale to get the decimal separator\.<br />Just remember that if you for example use "," as decimal sep, you should also change fmArrayColSep, fmFunctionSep and all vars with value=","|



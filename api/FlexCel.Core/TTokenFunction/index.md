---
uid: TTokenFunction
description: TTokenFunction
---

# TTokenFunction Class

A function like "Sum" or "If"\.
Note that this token doesn't have arguments\. The arguments are stored in the TTokenList that contains this token, in the order they appear in the formula\.
So, for example, the formula "=Sum\(A1,B2\)" would return the following token list:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>1. TTokenCellAddress with Address = A1, 2. TTokenCellAddress with Address = B2, 3. TTokenFunction with FunctionName = "Sum" and ArgumentCount = 2</span></span>
<span class="line"><span></span></span></code></pre>

The first token is the first argument, the second token is the second argument, and the third token is the function itself\.
In many cases, arguments will appear as if they were reversed: If you follow the TokenList above in reverse order, you will reconstruct the text "=Sum\(B2,A1\)" instead of =Sum\(A1, B2\)\. So you need to be careful, because the first argument of the function is the one more far away from the FunctionToken\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenFunction = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string, Integer\)](Create.md#ttokenfunctioncreatestring-integer)<br />  [Create\(string, Integer, Boolean\)](Create.md#ttokenfunctioncreatestring-integer-boolean)<br />|


## Properties

|Name|Description|
|---|---|
|[FunctionName](FunctionName.md)|Name of the function represented by this token\.<br />|
|[ArgumentCount](ArgumentCount.md)|Number of arguments for this function\. Note that if the function has a fixed number of arguments, this parameter is ignored\.<br />|
|[IsUserDefined](IsUserDefined.md)|If true, the function is used defined, not built\-in in Excel\. Note that some built\-in functions from Excel 2003 like EOMonth, while available in Excel, are implemented as user\-defined functions \(they were available in ToolPacks like the Analysis ToolPack\)\.<br />|



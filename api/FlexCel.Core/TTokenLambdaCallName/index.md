---
uid: TTokenLambdaCallName
description: TTokenLambdaCallName
---

# TTokenLambdaCallName Class

This token is used when you call a name like "=MyName\(5\)" and MyName has a lambda function\.
Note that if a cell has the expression like "=Lambda\(x,x\)" then you will just get a simple [TTokenFunction](../TTokenFunction/index.md) with a name of "Lambda"\. This token only appears when using a name as a user\-defined function\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TTokenLambdaCallName = class(<a href="../TToken/index.md">TToken</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new TTokenLambdaCallName token\.<br />|


## Properties

|Name|Description|
|---|---|
|[ArgumentCount](ArgumentCount.md)|The number of arguments for the function\. The last argument is the Name to be called\. For example the function "=MyName\(4,3\) will have 3 arguments: 4, 3, and the name MyName\.<br />|



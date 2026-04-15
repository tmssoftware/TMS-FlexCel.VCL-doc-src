---
uid: TRecoveryInvalidNameError
description: TRecoveryInvalidNameError
---

# TRecoveryInvalidNameError Class

This error happens when in recovery mode and a name has to be ignored because it can't be read\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TRecoveryInvalidNameError = class(<a href="../TFlexCelErrorInfo/index.md">TFlexCelErrorInfo</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates a new instance\.<br />|


## Properties

|Name|Description|
|---|---|
|[FileName](FileName.md)|File with the invalid name\.<br />|
|[NameIndex](NameIndex.md)|Position of the invalid named range in the name table\.<br />|
|[ExceptionMsg](ExceptionMsg.md)|Exception error\.<br />|



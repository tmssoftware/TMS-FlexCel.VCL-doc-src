---
uid: TFlxMessages.ThrowException
description: TFlxMessages.ThrowException
---

# TFlxMessages\.ThrowException Method

## Overloads

* [TFlxMessages\.ThrowException\(TCondFmtError\)](#tflxmessagesthrowexceptiontcondfmterror)
* [TFlxMessages\.ThrowException\(TFlxErr, \)](#tflxmessagesthrowexceptiontflxerr-)

# TFlxMessages\.ThrowException\(TCondFmtError\)
Throws an Exception for a conditional format error\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TFlxMessages/index.md">TFlxMessages</a>.ThrowException(const err: <a href="../TCondFmtError.md">TCondFmtError</a>); static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**err**|[TCondFmtError](../TCondFmtError.md)||


## See also

* [TFlxMessages](../TFlxMessages/index.md)

# TFlxMessages\.ThrowException\(TFlxErr, \)
Throws a standard FlexCelException\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class procedure <a href="../TFlxMessages/index.md">TFlxMessages</a>.ThrowException(const ResName: <a href="../TFlxErr.md">TFlxErr</a>; const args: ); static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ResName**|[TFlxErr](../TFlxErr.md)|Error Code\.|
|const|**args**||Parameters for this error\.|


## See also

* [TFlxMessages](../TFlxMessages/index.md)


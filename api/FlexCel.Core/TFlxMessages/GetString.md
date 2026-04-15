---
uid: TFlxMessages.GetString
description: TFlxMessages.GetString
---

# TFlxMessages\.GetString Method

## Overloads

* [TFlxMessages\.GetString\(TFlxMessage\)](#tflxmessagesgetstringtflxmessage)
* [TFlxMessages\.GetString\(TCondFmtError\)](#tflxmessagesgetstringtcondfmterror)
* [TFlxMessages\.GetString\(TFlxErr, \)](#tflxmessagesgetstringtflxerr-)

# TFlxMessages\.GetString\(TFlxMessage\)
Returns a string from the FlxMessage enumeration\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxMessages/index.md">TFlxMessages</a>.GetString(const ResName: <a href="../TFlxMessage.md">TFlxMessage</a>): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ResName**|[TFlxMessage](../TFlxMessage.md)|Message code\.|


## Returns

Associated string\.

## See also

* [TFlxMessages](../TFlxMessages/index.md)

# TFlxMessages\.GetString\(TCondFmtError\)
Returns a string from the CondFmtError enumeration\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxMessages/index.md">TFlxMessages</a>.GetString(const ResName: <a href="../TCondFmtError.md">TCondFmtError</a>): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ResName**|[TCondFmtError](../TCondFmtError.md)|Message code\.|


## Returns

Associated string\.

## See also

* [TFlxMessages](../TFlxMessages/index.md)

# TFlxMessages\.GetString\(TFlxErr, \)
Returns a string based on the TFlxErr enumerator, formatted with args\.
This method is used to get an Exception error message\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">class function <a href="../TFlxMessages/index.md">TFlxMessages</a>.GetString(const ResName: <a href="../TFlxErr.md">TFlxErr</a>; const args: ): string; static; overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**ResName**|[TFlxErr](../TFlxErr.md)|Error Code\.|
|const|**args**||Parameters for this error\.|


## See also

* [TFlxMessages](../TFlxMessages/index.md)


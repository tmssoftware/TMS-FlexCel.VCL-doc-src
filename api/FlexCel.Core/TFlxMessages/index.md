---
uid: TFlxMessages
description: TFlxMessages
---

# TFlxMessages Record

FlexCel Native string Constants\. It reads the resources from the active locale, and returns the correct string\.
If your language is not supported and you feel like translating the messages, please send us a copy\. We will include it on the next FlexCel version\.


To add a new language:
1. Copy the file flxmsg\.resx to your language \(for example, flxmsg\.es\.resx to translate to Spanish\)
2. Edit the new file and change the messages\.<br />
3. Add the \.resx file to the FlexCel project





## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxMessages = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetString](GetString.md)|**Overloaded<br />**  [GetString\(TFlxMessage\)](GetString.md#tflxmessagesgetstringtflxmessage)<br />  [GetString\(TCondFmtError\)](GetString.md#tflxmessagesgetstringtcondfmterror)<br />  [GetString\(TFlxErr, \)](GetString.md#tflxmessagesgetstringtflxerr-)<br />|
|[ThrowException](ThrowException.md)|**Overloaded<br />**  [ThrowException\(TCondFmtError\)](ThrowException.md#tflxmessagesthrowexceptiontcondfmterror)<br />  [ThrowException\(TFlxErr, \)](ThrowException.md#tflxmessagesthrowexceptiontflxerr-)<br />|



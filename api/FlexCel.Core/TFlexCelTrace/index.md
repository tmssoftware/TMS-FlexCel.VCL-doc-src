---
uid: TFlexCelTrace
description: TFlexCelTrace
---

# TFlexCelTrace Record

This class reports al FlexCel non\-fatal errors\. Use it to diagnose when something is going wrong\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelTrace = record;</code></pre>

## Properties

|Name|Description|
|---|---|
|[Enabled](Enabled.md)|Set this to false if you want to prevent FlexCel from tracing non fatal errors\. Note that if you don't have any event attached to this class the result will be the same as having Enabled = false\.<br />|


## Events

|Name|Description|
|---|---|
|[OnError](OnError.md)|This event is called each time a non fatal error happens in FlexCel\. Hook an event listener to it to be notified when this happens\.<br />|



---
uid: TPdfTimestampHandler
description: TPdfTimestampHandler
---

# TPdfTimestampHandler Anonymous method

Sends a timestamp request to a Time Stamping Authority \(TSA\) and returns the answer\. The request is a DER encoded RFC 3161 TimeStampReq, and the answer is a DER encoded TimeStampResp\.

**FlexCel never connects to the internet by itself**: So you need to provide the internet access through this method\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

<pre><code class="lang-delphi hljs">TPdfTimestampHandler = reference to function(timeStampRequest: TBytes): TBytes;</code></pre>

---
uid: TCmsSigner.Write
description: TCmsSigner.Write
---

# TCmsSigner\.Write Method

This method is called each time new data is added to the pdf\. When overwriting this method, use it to incrementally calculate the hash of the data\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TCmsSigner/index.md">TCmsSigner</a>.Write(const buffer: ; const count: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**buffer**||Data written to the pdf\.|
|const|**count**|Integer|Number of bytes from buffer that will be written\.|


## Returns

The number of bytes written\.

## See also

* [TCmsSigner](../TCmsSigner/index.md)


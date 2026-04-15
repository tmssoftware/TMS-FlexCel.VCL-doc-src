---
uid: TPdfSigner.Write
description: TPdfSigner.Write
---

# TPdfSigner\.Write Method

This method is called each time new data is added to the pdf\. When overwriting this method, use it to incrementally calculate the hash of the data\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TPdfSigner/index.md">TPdfSigner</a>.Write(const Buffer: ; const Count: Integer): Integer; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Buffer**||Data written to the pdf\.|
|const|**Count**|Integer|Number of bytes from buffer that will be written\.|


## Returns

The number of bytes written\.

## See also

* [TPdfSigner](../TPdfSigner/index.md)


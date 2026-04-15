---
uid: TPdfWriter.Sign
description: TPdfWriter.Sign
---

# TPdfWriter\.Sign Method

Signs the pdf documents with the specified [TPdfSignature](../TPdfSignature/index.md) or [TPdfVisibleSignature](../TPdfVisibleSignature/index.md)\.

**Important:** This method will take ownership of the signature and free it when it ends\. Don't reuse the signature twice, and don't free it yourself\.
**Note:** This method must be called **before** calling [BeginDoc](BeginDoc.md)

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TPdfWriter/index.md">TPdfWriter</a>.Sign(const aSignature: <a href="../TPdfSignature/index.md">TPdfSignature</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSignature**|[TPdfSignature](../TPdfSignature/index.md)|Signature used for signing\. Set it to null to stop signing the next documents\.|


## See also

* [TPdfWriter](../TPdfWriter/index.md)


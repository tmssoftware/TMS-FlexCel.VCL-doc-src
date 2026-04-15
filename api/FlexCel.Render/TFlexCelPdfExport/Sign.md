---
uid: TFlexCelPdfExport.Sign
description: TFlexCelPdfExport.Sign
---

# TFlexCelPdfExport\.Sign Method

Signs the pdf documents with the specified [TPdfSignature](../../FlexCel.Pdf/TPdfSignature/index.md) or [TPdfVisibleSignature](../../FlexCel.Pdf/TPdfVisibleSignature/index.md)\.
**Note:** This method must be called **before** calling [BeginExport](BeginExport.md)

## Syntax

**Unit:** [FlexCel.Render](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelPdfExport/index.md">TFlexCelPdfExport</a>.Sign(const aSignature: <a href="../../FlexCel.Pdf/TPdfSignature/index.md">TPdfSignature</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSignature**|[TPdfSignature](../../FlexCel.Pdf/TPdfSignature/index.md)|Signature used for signing\. Set it to null to stop signing the next documents\.|


## See also

* [TFlexCelPdfExport](../TFlexCelPdfExport/index.md)


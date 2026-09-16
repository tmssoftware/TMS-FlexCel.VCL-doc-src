---
uid: TPdfSignerFactory
description: TPdfSignerFactory
---

# TPdfSignerFactory Class

Override this factory when creating your own [TPdfSigner](../TPdfSigner/index.md) class, so it is returned here\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfSignerFactory = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CreateSigner](CreateSigner.md)|This method should return an instance of your customized [TPdfSigner](../TPdfSigner/index.md) class\.<br />|


## Properties

|Name|Description|
|---|---|
|[SubFilter](SubFilter.md)|Format of the signatures returned by the [TPdfSigner](../TPdfSigner/index.md) instances this factory creates\. It is written to the "SubFilter" entry of the pdf signature dictionary\. The default implementation returns [TPdfSignature&#8203;SubFilter.&#8203;Adbe&#8203;Pkcs7Detached](../TPdfSignatureSubFilter.md); override it if your signer creates CAdES signatures\.<br />|



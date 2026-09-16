---
uid: TBuiltInSignerFactory
description: TBuiltInSignerFactory
---

# TBuiltInSignerFactory Class

This class will create instances of the Built\-in signer\. It will take ownership of the signer you assign to it\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TBuiltInSignerFactory = class(<a href="../TPdfSignerFactory/index.md">TPdfSignerFactory</a>);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(TCmsSigner\)](Create.md#tbuiltinsignerfactorycreatetcmssigner)<br />  [Create\(TCmsSigner, TPdfSignatureSubFilter\)](Create.md#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter)<br />  [Create\(TCmsSigner, TPdfSignatureSubFilter, TCmsTimestampHandler\)](Create.md#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter-tcmstimestamphandler)<br />  [Create\(TCmsSigner, TPdfSignatureSubFilter, IPdfTimestampSettings\)](Create.md#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter-ipdftimestampsettings)<br />|


## Methods

|Name|Description|
|---|---|
|[CreateSigner](CreateSigner.md)|Creates a new Builtin Signer\.<br />|


## Properties

|Name|Description|
|---|---|
|[SubFilter](SubFilter.md)|Format of the signatures created by this factory\. See [TPdfSignature&#8203;SubFilter](../TPdfSignatureSubFilter.md)\.<br />|



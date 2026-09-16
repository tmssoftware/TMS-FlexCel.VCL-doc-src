---
uid: TBuiltInSignerFactory.Create
description: TBuiltInSignerFactory.Create
---

# TBuiltInSignerFactory\.Create Constructor

## Overloads

* [TBuiltInSignerFactory\.Create\(TCmsSigner\)](#tbuiltinsignerfactorycreatetcmssigner)
* [TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter\)](#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter)
* [TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter, TCmsTimestampHandler\)](#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter-tcmstimestamphandler)
* [TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter, IPdfTimestampSettings\)](#tbuiltinsignerfactorycreatetcmssigner-tpdfsignaturesubfilter-ipdftimestampsettings)

# TBuiltInSignerFactory\.Create\(TCmsSigner\)
Creates a new instance of this class, creating "/adbe\.pkcs7\.detached" signatures\.

This default is old\. Consider using another overload and setting the SubFilter to EtsiCAdESDetached

## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBuiltInSignerFactory/index.md">TBuiltInSignerFactory</a>.Create(const aSigner: <a href="../../FlexCel.Core/TCmsSigner/index.md">TCmsSigner</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSigner**|[TCmsSigner](../../FlexCel.Core/TCmsSigner/index.md)|CmsSigner used to sign the pdf files\.<br />**IMPORTANT**: This class will take ownership of the signer and free it\.<br />You shouldn't free the signer yourself\.|


## See also

* [TBuiltInSignerFactory](../TBuiltInSignerFactory/index.md)

# TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter\)
Creates a new instance of this class, creating signatures in the format specified in `aSubFilter`\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBuiltInSignerFactory/index.md">TBuiltInSignerFactory</a>.Create(const aSigner: <a href="../../FlexCel.Core/TCmsSigner/index.md">TCmsSigner</a>; const aSubFilter: <a href="../TPdfSignatureSubFilter.md">TPdfSignatureSubFilter</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSigner**|[TCmsSigner](../../FlexCel.Core/TCmsSigner/index.md)|CmsSigner used to sign the pdf files\.|
|const|**aSubFilter**|[TPdfSignature&#8203;SubFilter](../TPdfSignatureSubFilter.md)|Format of the signatures created by this factory\. See [SubFilter](SubFilter.md)\.<br />When it is [TPdfSignatureSubFilter.EtsiCAdESDetached](../TPdfSignatureSubFilter.md), the ESS signing\-certificate\-v2 signed attribute required by CAdES will be added to `aSigner` unless it already has an ESS signing certificate attribute of its own\.|


## See also

* [TBuiltInSignerFactory](../TBuiltInSignerFactory/index.md)

# TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter, TCmsTimestampHandler\)
USe this overload for creating timestamped \(PAdES B\-T\) signatures\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBuiltInSignerFactory/index.md">TBuiltInSignerFactory</a>.Create(const aSigner: <a href="../../FlexCel.Core/TCmsSigner/index.md">TCmsSigner</a>; const aSubFilter: <a href="../TPdfSignatureSubFilter.md">TPdfSignatureSubFilter</a>; const aTimestamper: TCmsTimestampHandler);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSigner**|[TCmsSigner](../../FlexCel.Core/TCmsSigner/index.md)|CmsSigner used to sign the pdf files\.|
|const|**aSubFilter**|[TPdfSignature&#8203;SubFilter](../TPdfSignatureSubFilter.md)|Format of the signatures created by this factory\. See [SubFilter](SubFilter.md)\.|
|const|**aTimestamper**|TCmsTimestampHandler|Code that requests the timestamp from a TSA and returns its answer\. FlexCel never connects to the internet, so you need to contact the TSA here and return the answer\. Leave it null to create a plain PAdES B\-B signature \(without a timestamp\)\. Use the [IPdfTimestampSettings](../IPdfTimestampSettings/index.md) overload when you want to choose the digest, the space reserved for the token, or to share the measured token size between the factories using the same TSA\.|


## See also

* [TBuiltInSignerFactory](../TBuiltInSignerFactory/index.md)

# TBuiltInSignerFactory\.Create\(TCmsSigner, TPdfSignatureSubFilter, IPdfTimestampSettings\)
Creates a new instance of this class, creating timestamped \(PAdES B\-T\) signatures\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TBuiltInSignerFactory/index.md">TBuiltInSignerFactory</a>.Create(const aSigner: <a href="../../FlexCel.Core/TCmsSigner/index.md">TCmsSigner</a>; const aSubFilter: <a href="../TPdfSignatureSubFilter.md">TPdfSignatureSubFilter</a>; aTimestampSettings: <a href="../IPdfTimestampSettings/index.md">IPdfTimestampSettings</a>);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSigner**|[TCmsSigner](../../FlexCel.Core/TCmsSigner/index.md)|CmsSigner used to sign the pdf files\.|
|const|**aSubFilter**|[TPdfSignature&#8203;SubFilter](../TPdfSignatureSubFilter.md)|Format of the signatures created by this factory\. See [SubFilter](SubFilter.md)\.|
||**aTimestampSettings**|[IPdfTimestamp&#8203;Settings](../IPdfTimestampSettings/index.md)|How the signatures are timestamped\. Leave it null to create plain PAdES B\-B signatures\. **Note** that FlexCel needs to know how big the tokens of your TSA are before it can sign, so the first document asks the TSA for one extra token\. Set [IPdfTimestampSettings.TokenSizeHint](../IPdfTimestampSettings/TokenSizeHint.md) when you already know the size and want to avoid it\.|


## See also

* [TBuiltInSignerFactory](../TBuiltInSignerFactory/index.md)


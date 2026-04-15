---
uid: TEncryptionFactory.GetSigner
description: TEncryptionFactory.GetSigner
---

# TEncryptionFactory\.GetSigner Method

Returns the signer needed to sign a pdf file\. **If not assigned to a SignerFactory**, you need to destroy the class returned by this method once you are done using it\.

When you assign it to a [TPdfSignerFactory](../../FlexCel.Pdf/TPdfSignerFactory/index.md), then the signed factory will take ownership of the signer\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TEncryptionFactory/index.md">TEncryptionFactory</a>.GetSigner(const Certificates: TArray&lt;<a href="../TX509Certificate2/index.md">TX509Certificate2</a>&gt;; const AlgorithmOid: string): <a href="../TCmsSigner/index.md">TCmsSigner</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Certificates**|TArray\<[TX509Certificate2](../TX509Certificate2/index.md)>|Array of certificates used for signing\. The current built\-in implementation in FlexCel requires one single certificate in the array\.|
|const|**AlgorithmOid**|string|Optional algorithm identifier\. If left empty FlexCel will use SHA512 \('1\.2\.840\.113549\.1\.1\.13'\) which is szOID\_RSA\_SHA512RSA\. You could choose a different algorithm from the list of supported CryptoAPI algorithms here: https://msdn\.microsoft\.com/en\-us/library/windows/desktop/aa381133\(v=vs\.85\)\.aspx if SHA512 became compromised \(As SHA1 did in the past\)\.|


## Returns

A signer to sign a pdf file\. Remember that this class must be freed \*\*only\*\* if not assigned to a SignerFactory\.

## See also

* [TEncryptionFactory](../TEncryptionFactory/index.md)


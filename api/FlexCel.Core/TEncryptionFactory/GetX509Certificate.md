---
uid: TEncryptionFactory.GetX509Certificate
description: TEncryptionFactory.GetX509Certificate
---

# TEncryptionFactory\.GetX509Certificate Method

Loads a X509Certificate from a pfx byte array\. You need to destroy the class returned by this method once you are done using it\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TEncryptionFactory/index.md">TEncryptionFactory</a>.GetX509Certificate(const Data: TBytes; const Password: string): <a href="../TX509Certificate2/index.md">TX509Certificate2</a>; virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**Data**|TBytes|A byte array with the data of a pfx file\. To load the data from disk, you can use TFile\.ReadAllBytes\(FileName\.pfx\)|
|const|**Password**|string|Password to open the pfx file\.|


## Returns

A certificate to sign a pdf file\. Remember to free this class once it is used\.

## See also

* [TEncryptionFactory](../TEncryptionFactory/index.md)


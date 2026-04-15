---
uid: TEncryptionFactory
description: TEncryptionFactory
---

# TEncryptionFactory Class

This class encapsulates what we need to support encryption routines\. You can derive from this class and override the methods to return your own encryption classes\. then you need to assign the static variable EncryptionFactory to your descendant class, and FlexCel will then use the new classes\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TEncryptionFactory = class(TObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetX509Certificate](GetX509Certificate.md)|Loads a X509Certificate from a pfx byte array\. You need to destroy the class returned by this method once you are done using it\.<br />|
|[GetSigner](GetSigner.md)|Returns the signer needed to sign a pdf file\. **If not assigned to a SignerFactory**, you need to destroy the class returned by this method once you are done using it\.<br /><br />When you assign it to a [TPdfSignerFactory](../../FlexCel.Pdf/TPdfSignerFactory/index.md), then the signed factory will take ownership of the signer\.<br />|



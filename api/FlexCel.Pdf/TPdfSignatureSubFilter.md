---
uid: TPdfSignatureSubFilter
description: TPdfSignatureSubFilter
---

# TPdfSignatureSubFilter Enumeration

Format of the digital signature embedded in a PDF file\. This is the value written to the "SubFilter" entry of the signature dictionary, and it tells the PDF reader how the bytes returned by [TPdfSigner.GetSignature](TPdfSigner/GetSignature.md) have to be interpreted\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|AdbePkcs7Detached|0|"/adbe\.pkcs7\.detached": A detached PKCS\#7 \(CMS\) SignedData object, as defined in the PDF specification\.<br />This is the default\.<br />|
|EtsiCAdESDetached|1|"/ETSI\.CAdES\.detached": A detached CAdES SignedData object, as defined by PAdES \(ETSI EN 319 142\)\.<br />Use this format when you need a signature compliant with the European eIDAS regulation\.<br />**Note:** The bytes returned by [TPdfSigner.GetSignature](TPdfSigner/GetSignature.md) must be a CAdES\-BES \(or better\) signature, which among other things means that the signed attributes must include the ESS signing\-certificate\-v2 attribute\. [TBuiltInSignerFactory](TBuiltInSignerFactory/index.md) takes care of this for you, but if you wrote your own [TPdfSigner](TPdfSigner/index.md) you need to ensure it yourself\.<br />|



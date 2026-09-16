---
uid: TPdfSignature
description: TPdfSignature
---

# TPdfSignature Class

Describes a non visible signature for a PDF file\.
For a visible signature, use [TPdfVisibleSignature](../TPdfVisibleSignature/index.md)
**NOTE:** This class will take ownership of the signer factory and will free it once it is used\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfSignature = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|Creates an invisible signature\. For a visible signature, create a [TPdfVisibleSignature](../TPdfVisibleSignature/index.md) class\.<br />|


## Properties

|Name|Description|
|---|---|
|[AllowedChanges](AllowedChanges.md)|Specifies which changes are allowed in the signed pdf\. It is only used when [Certify](Certify.md) is true: an approval signature doesn't declare any policy\.<br />|
|[Certify](Certify.md)|If true \(the default\) then the signature certifies the document\.<br />Besides signing the document, the signature declares which changes are allowed later \(see [AllowedChanges](AllowedChanges.md)\), and the viewer is expected to enforce it\.<br />A document can have only one certification signature, and it must be the first one\.<br /><br />Set it to false to create a plain approval signature instead: the document is still signed, and any later change is still detected, but there is no author policy for the viewer to enforce, and[...[more]](Certify.md)|
|[ContactInfo](ContactInfo.md)|Information provided by the signer to enable a recipient to contact the signer to verify the signature; for example, a phone number\.<br />|
|[Location](Location.md)|The CPU host name or physical location of the signing\. Leave it null for not specifying a location\.<br />|
|[Name](Name.md)|Name to be given to the signature\. This will be displayed in the "signatures" tab, and acrobat normally names it "Signature"\.<br />It cannot be null\.<br />**Note:** Signature names cannot contain dots\. An exception will be thrown if you try to enter a name with a dot here\.<br />|
|[Reason](Reason.md)|The reason for the signing, such as "I agree\.\.\."\. Leave it null if you do not want to specify a reason\.<br />|
|[SignDate](SignDate.md)|Sign Date\. Use DateTime\.MinValue to use the current date\.<br />|
|[SignerFactory](SignerFactory.md)|Object that implements the actual signing\.<br />|



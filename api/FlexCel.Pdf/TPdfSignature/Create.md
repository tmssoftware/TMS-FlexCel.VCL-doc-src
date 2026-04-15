---
uid: TPdfSignature.Create
description: TPdfSignature.Create
---

# TPdfSignature\.Create Constructor

Creates an invisible signature\. For a visible signature, create a [TPdfVisibleSignature](../TPdfVisibleSignature/index.md) class\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TPdfSignature/index.md">TPdfSignature</a>.Create(const aSignerFactory: <a href="../TPdfSignerFactory/index.md">TPdfSignerFactory</a>; const aName: string; const aReason: string; const aLocation: string; const aContactInfo: string);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSignerFactory**|[TPdfSignerFactory](../TPdfSignerFactory/index.md)|See [SignerFactory](SignerFactory.md)<br />**NOTE:** This class will take ownership of the signer factory and will free it once it is used\.|
|const|**aName**|string|See [Name](Name.md)|
|const|**aReason**|string|See [Reason](Reason.md)|
|const|**aLocation**|string|See [Location](Location.md)|
|const|**aContactInfo**|string|See [ContactInfo](ContactInfo.md)|


## See also

* [TPdfSignature](../TPdfSignature/index.md)


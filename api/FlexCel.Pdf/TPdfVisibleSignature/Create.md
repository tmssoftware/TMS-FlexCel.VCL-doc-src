---
uid: TPdfVisibleSignature.Create
description: TPdfVisibleSignature.Create
---

# TPdfVisibleSignature\.Create Constructor

Creates a new visible signature for a PDF file\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">constructor <a href="../TPdfVisibleSignature/index.md">TPdfVisibleSignature</a>.Create(const aSignerFactory: <a href="../TPdfSignerFactory/index.md">TPdfSignerFactory</a>; const aName: string; const aReason: string; const aLocation: string; const aContactInfo: string; const aPage: Integer; const aRect: <a href="../../FlexCel.Core/TUIRectangle/index.md">TUIRectangle</a>; const aImageData: TBytes);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**aSignerFactory**|[TPdfSignerFactory](../TPdfSignerFactory/index.md)|See [TPdfSignature.SignerFactory](../TPdfSignature/SignerFactory.md)|
|const|**aName**|string|See [TPdfSignature.Name](../TPdfSignature/Name.md)|
|const|**aReason**|string|See [TPdfSignature.Reason](../TPdfSignature/Reason.md)|
|const|**aLocation**|string|See [TPdfSignature.Location](../TPdfSignature/Location.md)|
|const|**aContactInfo**|string|See [TPdfSignature.ContactInfo](../TPdfSignature/ContactInfo.md)|
|const|**aPage**|Integer|See [Page](Page.md)|
|const|**aRect**|[TUIRectangle](../../FlexCel.Core/TUIRectangle/index.md)|See [Rect](Rect.md)|
|const|**aImageData**|TBytes|See [ImageData](ImageData.md)|


## See also

* [TPdfVisibleSignature](../TPdfVisibleSignature/index.md)


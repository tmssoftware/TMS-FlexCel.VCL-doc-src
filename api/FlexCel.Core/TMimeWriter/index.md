---
uid: TMimeWriter
description: TMimeWriter
---

# TMimeWriter Class

A simple class used to create MIME formatted messages\. While it does not provide much functionality, it gives enough to create simple multipart archives\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TMimeWriter = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[CreateMultiPart&#8203;Message](CreateMultiPartMessage.md)|Creates the headers for a multipart MIME file\. This must be the first method to call in order to create a MIME file\.<br />After this, you need to call [AddPartHeader](AddPartHeader.md) and start adding the parts of the message, and you **always** need to end the message by calling [EndMultiPartMessage](EndMultiPartMessage.md)\.<br />|
|[AddPartHeader](AddPartHeader.md)|Adds the header for a part in a multipart Mime message\. After calling this method, you need to write your data content into the TFlexCelWriter using [WriteQuotedPrintable](WriteQuotedPrintable.md) or [WriteBase64](WriteBase64.md) and after that always call [EndPart](EndPart.md)\.<br />|
|[EndPart](EndPart.md)|Ends a MIME part started with [AddPartHeader](AddPartHeader.md)\.<br />|
|[EndMultiPartMessage](EndMultiPartMessage.md)|Call this method after the last call to EndPart, to finish the MIME message\.<br />|
|[QEncode](QEncode.md)|Returns the Q\-encode of a string, used in the MIME Headers\.  //RFC 2047|
|[WriteQuotedPrintable](WriteQuotedPrintable.md)|Writes the Quoted Printable encoding of a string, as defined in RFC 2045 section 6\.7 This method keeps state and breaks the line  every time it is longer than 76 characters\.<br />The state is reset each time [AddPartHeader](AddPartHeader.md) is called\.<br />|
|[WriteBase64](WriteBase64.md)|Writes the base64 encoding of a byte array, as defined in RFC 2045 section 6\.8 This method does not keep the state, so all binary data must be supplied at once\.<br />This method will also correctly split the string at 76 characters\.<br />|



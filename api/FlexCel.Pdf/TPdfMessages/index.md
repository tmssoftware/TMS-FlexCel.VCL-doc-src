---
uid: TPdfMessages
description: TPdfMessages
---

# TPdfMessages Record

FlexCel Native PDF Constants\. It reads the resources from the active locale, and returns the correct string\.
If your language is not supported and you feel like translating the messages, please send us a copy\. We will include it on the next FlexCel version\.


To add a new language:
1. Copy the file pdfmsg\.resx to your language \(for example, pdfmsg\.es\.resx to translate to spanish\)
2. Edit the new file and change the messages\.<br />
3. Add the \.resx file to the FlexCel project





## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">TPdfMessages = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[GetString](GetString.md)|Reruns a string based on the PdfErr enumerator, formatted with args\.<br />This method is used to get an Exception error message\.<br />|
|[ThrowException](ThrowException.md)|Throws a standard FlexCelPdfException\.&#8203;<br />|



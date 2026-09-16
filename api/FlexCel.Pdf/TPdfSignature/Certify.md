---
uid: TPdfSignature.Certify
description: TPdfSignature.Certify
---

# TPdfSignature\.Certify Property

If true \(the default\) then the signature certifies the document\.
Besides signing the document, the signature declares which changes are allowed later \(see [AllowedChanges](AllowedChanges.md)\), and the viewer is expected to enforce it\.
A document can have only one certification signature, and it must be the first one\.

Set it to false to create a plain approval signature instead: the document is still signed, and any later change is still detected, but there is no author policy for the viewer to enforce, and [AllowedChanges](AllowedChanges.md) is not used\. Approval signatures are the ones to use when the document is meant to be annotated, filled, or signed by others\. They don't show the "certified by" bar in Acrobat\.

Look at ['Signing pdf files' in the Pdf Exporting Guide](xref:PdfExportingGuide#signing-pdf-files) for more information\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfSignature/index.md">TPdfSignature</a>.Certify: Boolean</code></pre>

## See also

* [TPdfSignature](../TPdfSignature/index.md)


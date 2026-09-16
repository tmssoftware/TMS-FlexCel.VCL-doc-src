---
uid: IPdfTeardownTagger
description: IPdfTeardownTagger
---

# IPdfTeardownTagger Interface

Implement this interface to tag a PDF file created by TPdfWriter\. This interface will be called after every document is finished and allows you to write global tags\. Note that FlexCelPdfExport already implements it, so there is no need to define it again\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">IPdfTeardownTagger = interface(<a href="../IPdfTagger/index.md">IPdfTagger</a>);</code></pre>


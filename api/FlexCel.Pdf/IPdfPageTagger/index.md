---
uid: IPdfPageTagger
description: IPdfPageTagger
---

# IPdfPageTagger Interface

Implement this interface in order to tag a pdf file created by TPdfWriter\. This interface will be called after every page is generated\. Note that FlexCelPdfExport already implements it so there is no need to define it again\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">IPdfPageTagger = interface(<a href="../IPdfTagger/index.md">IPdfTagger</a>);</code></pre>

## Methods

|Name|Description|
|---|---|
|[AddContentTag](AddContentTag.md)|Adds a new tag to the structure tree, with a child which was added with TagContentBegin/&#8203;Tag&#8203;Content&#8203;End\.&#8203;<br />|



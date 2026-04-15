---
uid: IPdfTagActions.TagsInPage
description: IPdfTagActions.TagsInPage
---

# IPdfTagActions\.TagsInPage Method

This event will be called after each page is completed, and allows you to specify the tags for the page\.
All tags in the page should be defined here\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../IPdfTagActions/index.md">IPdfTagActions</a>.TagsInPage(const pageNumber: Integer; const tagger: <a href="../IPdfPageTagger/index.md">IPdfPageTagger</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**pageNumber**|Integer|Page that we are currently exporting\.|
|const|**tagger**|[IPdfPageTagger](../IPdfPageTagger/index.md)|Object for setting up the tags\.|


## See also

* [IPdfTagActions](../IPdfTagActions/index.md)


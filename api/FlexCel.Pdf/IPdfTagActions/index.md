---
uid: IPdfTagActions
description: IPdfTagActions
---

# IPdfTagActions Interface

Events that allow you to tag a pdf document\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">IPdfTagActions = interface(IInterface);</code></pre>

## Methods

|Name|Description|
|---|---|
|[DefineRoles](DefineRoles.md)|This event allows you to define alias roles\.<br />|
|[TagsInPage](TagsInPage.md)|This event will be called after each page is completed and allows you to specify the tags for the page\.<br />All tags on the page should be defined here\.<br />|
|[TagsTeardown](TagsTeardown.md)|This event will be called before finalizing the document and allows you to specify the global tags on it\.<br />|



---
uid: TDocumentProperties.PreserveCreationDate
description: TDocumentProperties.PreserveCreationDate
---

# TDocumentProperties.PreserveCreationDate Property

By default FlexCel will set the creation date in the file to be the date when you actually created it, no matter the value originally stored in the file\.
This assumes you are starting from a template and generating a new document from it\.
But if you are modifying an existing file and want to preserve the original creation date, then you need to set this property to true\. **Note that this property sets itself automatically to true if you manually set the creation time of a file\.
**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDocumentProperties/index.md">TDocumentProperties</a>.PreserveCreationDate: Boolean</code></pre>

## See also

* [TDocumentProperties](../TDocumentProperties/index.md)


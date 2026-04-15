---
uid: TDocumentProperties.PreserveModifiedDate
description: TDocumentProperties.PreserveModifiedDate
---

# TDocumentProperties.PreserveModifiedDate Property

By default FlexCel will set the modified date in the file to be the date when you actually saved it, no matter the value originally stored in the file\.
But if you need to set a different modified date than the date in the server, or you don't want a new modified date to be saved and preserve the one in the document,  then you need to set this property to true\.
If you are setting this property to true, you probably also want to set [PreserveCreationDate](PreserveCreationDate.md) to true\.
**Note that this property sets itself automatically to true if you manually set the modified time of a file\.
**

## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDocumentProperties/index.md">TDocumentProperties</a>.PreserveModifiedDate: Boolean</code></pre>

## See also

* [TDocumentProperties](../TDocumentProperties/index.md)


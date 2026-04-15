---
uid: TPdfWriter.PageSize
description: TPdfWriter.PageSize
---

# TPdfWriter.PageSize Property

Page size of the active page\. You can change it \*before\* calling NewPage\(\) and it will change for the new sheets\.
Note that once NewPage\(\) \(or BeginDoc\(\) for the first page\) is called, the page size will remain constant for that page\.
This property must be changed before\.


## Syntax

**Unit:** [FlexCel.Pdf](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TPdfWriter/index.md">TPdfWriter</a>.PageSize: <a href="../../FlexCel.Core/TPaperDimensions/index.md">TPaperDimensions</a></code></pre>

## See also

* [TPdfWriter](../TPdfWriter/index.md)


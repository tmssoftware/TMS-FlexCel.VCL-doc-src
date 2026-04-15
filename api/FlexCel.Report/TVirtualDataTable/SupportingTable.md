---
uid: TVirtualDataTable.SupportingTable
description: TVirtualDataTable.SupportingTable
---

# TVirtualDataTable\.SupportingTable Method

This method should return the underlying table used to access the data if there is one\.
This will normally return the same instance, but in TOPN and ATLEAST datasets it returns the table used to calculate them\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>.SupportingTable: <a href="../TVirtualDataTable/index.md">TVirtualDataTable</a>; virtual;</code></pre>

## See also

* [TVirtualDataTable](../TVirtualDataTable/index.md)


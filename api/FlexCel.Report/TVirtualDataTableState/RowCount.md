---
uid: TVirtualDataTableState.RowCount
description: TVirtualDataTableState.RowCount
---

# TVirtualDataTableState.RowCount Property

Returns the number of rows available on the dataset, for the current state\. Note that this method can be called many times, so it should be fast\.
Use a cache if necessary\. Do \*not\* use something like "return select count\(\*\) from table" here, it would be too slow\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.RowCount: Integer</code></pre>

## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)


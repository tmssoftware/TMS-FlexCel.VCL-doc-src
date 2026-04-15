---
uid: TVirtualDataTableState.Eof
description: TVirtualDataTableState.Eof
---

# TVirtualDataTableState\.Eof Method

This method returns if we have reached the last record in the table\. The default implementation just sees if [Position](Position.md) = [RowCount](RowCount.md)\. If RowCount is slow and you have a  faster way to know if you are at the end, override this method\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">function <a href="../TVirtualDataTableState/index.md">TVirtualDataTableState</a>.Eof: Boolean; virtual;</code></pre>

## See also

* [TVirtualDataTableState](../TVirtualDataTableState/index.md)


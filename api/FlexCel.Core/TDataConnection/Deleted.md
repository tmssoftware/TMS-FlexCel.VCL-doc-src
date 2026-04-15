---
uid: TDataConnection.Deleted
description: TDataConnection.Deleted
---

# TDataConnection.Deleted Property

Indicates whether the associated workbook connection has been deleted\.
Deleted connections contain only the attributes name and deleted=true, all other information is removed when saving the file\.
If a new connection is created with the same name as a deleted connection, then the deleted connection is overwritten by the new connection\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDataConnection/index.md">TDataConnection</a>.Deleted: Boolean</code></pre>

## See also

* [TDataConnection](../TDataConnection/index.md)


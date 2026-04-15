---
uid: TDataConnection.SaveData
description: TDataConnection.SaveData
---

# TDataConnection.SaveData Property

True if the external data fetched over the connection to populate a table is to be saved with the workbook; otherwise, false\.
This exists for data security purposes \- if no external data is saved in \(or "cached"\) in the workbook, then current user credentials can be required every time to retrieve the relevant data, and people won't see the data the workbook author had last been using before saving the file\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDataConnection/index.md">TDataConnection</a>.SaveData: Boolean</code></pre>

## See also

* [TDataConnection](../TDataConnection/index.md)


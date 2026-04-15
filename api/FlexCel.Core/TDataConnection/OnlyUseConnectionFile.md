---
uid: TDataConnection.OnlyUseConnectionFile
description: TDataConnection.OnlyUseConnectionFile
---

# TDataConnection.OnlyUseConnectionFile Property

Indicates whether the spreadsheet application should always and only use the connection information in the external connection file indicated by the odcFile attribute when the connection is refreshed\.
If false, then the spreadsheet application should follow the procedure indicated by the reconnectionMethod attribute\.

Applies to ODBC connections, and may be applied to custom data connections\.This attribute is ignored for other types of connections\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TDataConnection/index.md">TDataConnection</a>.OnlyUseConnectionFile: Boolean</code></pre>

## See also

* [TDataConnection](../TDataConnection/index.md)


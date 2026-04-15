---
uid: TFlexCelReport.AddConnection
description: TFlexCelReport.AddConnection
---

# TFlexCelReport\.AddConnection Method

Adds an adapter to use from the template on the DIRECT SQL commands\.
**For security reasons, make sure this adapter ONLY GRANTS READONLY ACCESS TO THE DATA**

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddConnection(const connectionName: string; const adapter: TFlexCelSQLQueryMethod; const recordCountMode: <a href="../TRecordCountMode.md">TRecordCountMode</a> = TRecordCountMode.Normal); overload;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**connectionName**|string|This is the name you will use on the template to refer to this adapter\.|
|const|**adapter**|TFlexCelSQLQueryMethod|A method that will execute a query when needed\.|
|const|**recordCountMode**|[TRecordCountMode](../TRecordCountMode.md)|**Optional**: Default value is TRecordCountMode.Normal<br /><br />USe it to set how FlexCel will count the records returned by the query\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


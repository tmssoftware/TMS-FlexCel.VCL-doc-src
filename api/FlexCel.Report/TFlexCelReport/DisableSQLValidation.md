---
uid: TFlexCelReport.DisableSQLValidation
description: TFlexCelReport.DisableSQLValidation
---

# TFlexCelReport.DisableSQLValidation Property

If false \(the default\) FlexCelReport will only allow DirectSQL queries that begin with "SELECT", to avoid people doing inserts or deletes from the config sheet\.
If true, FlexCelReport will pass the DirectSQL queries you write in the config sheet directly to the server\.
**Caution:** Setting this property to true might have security implications\. Take a look at the remarks\.


## Remarks

You can disable the SQL validation if for example you want to read data from stored procedures in SQL Server\.
While most databases will allow you to do a Select from a stored procedure, in SQL server you'll need to call "EXEC"\.
For example:

<pre class="shiki shiki-themes light-plus dark-plus" style="background-color:#FFFFFF;--shiki-dark-bg:#1E1E1E;color:#000000;--shiki-dark:#D4D4D4" tabindex="0"><code><span class="line"><span>sql(conn; exec GetOrders)</span></span>
<span class="line"><span></span></span></code></pre>

But note that if you disable SQL validation, you'll be letting the user run any arbitrary stored procedure in the server, or insert, update or delete records\. In both cases, either with SQL validation true or false, you'll want to give the  users a readonly connection with permissions only to the objects they need so they can't modify stuff in the database with the template\. But if you disable SQL validation, then there is one less barrier to users modifying data in the database from the report\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.DisableSQLValidation: Boolean</code></pre>

## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


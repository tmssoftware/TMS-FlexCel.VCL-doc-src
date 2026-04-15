---
uid: TFlexCelReport.AddSqlParameter
description: TFlexCelReport.AddSqlParameter
---

# TFlexCelReport\.AddSqlParameter Method

Adds an SQL parameter to use from the template on the DIRECT SQL commands\.
Note that the parameter must have a name even if you are using positional parameters \("?"\) because on the template you should always write named parameters\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.AddSqlParameter(const parameterName: string; const parameter: TFlexCelSQLParameterMethod);</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**parameterName**|string|The name of the parameter without special symbols, as it is written on the DIRECT SQL string\. This might be different from the real parameter name\.<br />For example, on SQL Server, parameterName might be "MyParameter" while parameter\.ParameterName would be "@MyParameter"|
|const|**parameter**|TFlexCelSQLParameterMethod|The parameter to add\.|


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


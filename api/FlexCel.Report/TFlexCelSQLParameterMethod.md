---
uid: TFlexCelSQLParameterMethod
description: TFlexCelSQLParameterMethod
---

# TFlexCelSQLParameterMethod Anonymous method

Use this method to assign the SQL parameters in a query\.
"paramName": This is the parameter we are setting\. This  name doesn't include the ":" or "@" prefix for the parameter\.


"dataset": This is the dataset where you need to assign the parameter\. You will need to cast this value to the specific TDataSet you created in TFlexCelSQLQueryMethod, and assign the parameter there\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

<pre><code class="lang-delphi hljs">TFlexCelSQLParameterMethod = reference to procedure(const paramName: string; const dataset: TDataSet);</code></pre>

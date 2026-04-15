---
uid: TFlexCelReport.SqlParameterReplace
description: TFlexCelReport.SqlParameterReplace
---

# TFlexCelReport.SqlParameterReplace Property

Format string for replacing the standard parameter names on DIRECT SQL commands\. You can leave it empty for ODBC, OLEDB or SQLSERVER databases\.
See Also [SqlParametersType](SqlParametersType.md)

## Remarks

On ADO\.NET sql parameters can be defined on multiple ways, depending on the database you use\.
For example, SQL Server will use "@ParamName", while OLEDB will use "?" as parameter id\.
But, to keep templates database independent, you will always use  "@ParamName" notation on the Direct SQL commands you write on templates\.
When using OLEDB, ODBC or SqlSever, FlexCel knows how to  replace the correct parameters on the SQL on templates, but for more generic databases you might need to use this property\.
This is a standard \.NET format string, where \{0\} will be replaced by the parameter name\. For example,  on Oracle database you might need to set this value to ":\{0\}" \(without quotes\) that will translate on ":ParamName"

## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TFlexCelReport/index.md">TFlexCelReport</a>.SqlParameterReplace: string</code></pre>

## Examples

On oracle databases, you can set this property to ":\{0\}" \(without quotes\) It will create parameters of type ":ParamName"\.


## See also

* [TFlexCelReport](../TFlexCelReport/index.md)


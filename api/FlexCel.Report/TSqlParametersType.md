---
uid: TSqlParametersType
description: TSqlParametersType
---

# TSqlParametersType Enumeration

How the parameters for Direct SQL queries are\.
Change it only if your database uses positional parameters and it is not ODBC or OLEDB\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Automatic|0|FlexCel will try to guess the correct type\.<br />Currently it will return Positional for ODBC and OLEDB Parameters and Named for everything else\.<br />|
|Named|1|Parameter is named\. For example, "@param1" or ":Param2"|
|Positional|2|Name of parameter is not important, and we only care about position\.<br />For example "?"|



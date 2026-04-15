---
uid: TDataConnectionDbProperties
description: TDataConnectionDbProperties
---

# TDataConnectionDbProperties Class

This element stores all properties associated with an ODBC or OLE DB external data connection\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionDbProperties = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Connection](Connection.md)|The string used to initiate a session with a data source\.<br />|
|[Command](Command.md)|The string containing the database command to pass to the data provider that will interact with the external source in order to retrieve data\.<br />|
|[ServerCommand](ServerCommand.md)|Specifies a second command text string that is persisted when PivotTable server\-based page fields are in use\.<br />For ODBC connections, serverCommand is usually a broader query than command\(no WHERE clause is present in the former\)\. Based on these 2 commands, parameter UI can be populated and parameterized queries can be constructed\.<br />|
|[CommandType](CommandType.md)|Specifies the custom data source command type\. Values are passed to the custom data source provider and their meaning might change depending on the provider\.<br /><br /><br /><br />For example, for OLEDB, the values can be: 1\. Query specifies a cube name 2\. Query specifies a SQL statement 3\. Query specifies a table name 4\. Query specifies that default information has been given, and it is up to the provider how to interpret\.<br />5\. Query is against a web based List Data Provider<br /><br />|



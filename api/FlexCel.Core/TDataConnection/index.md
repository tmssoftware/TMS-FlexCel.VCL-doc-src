---
uid: TDataConnection
description: TDataConnection
---

# TDataConnection Class

This class represents one data connection on the workbook\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnection = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if obj is the same as this object\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[DbProperties](DbProperties.md)|This element stores all properties associated with an ODBC or OLE DB external data connection\.<br />|
|[OlapProperties](OlapProperties.md)|This element contains all the properties needed for an OLAP data connection\. OLAP connections contain both the [TDataConnection&#8203;DbProperties](../TDataConnectionDbProperties/index.md) and TDataConnection&#8203;Olap&#8203;Properties child elements\.<br />|
|[WebQueryProperties](WebQueryProperties.md)|This element specifies the properties for a web query source\. A web query will retrieve data from HTML tables, and can also supply HTTP "Get" parameters to be processed by the web server in generating the HTML by including the parameters and parameter elements\.<br />|
|[TextImportProperties](TextImportProperties.md)|This element contains all of the text import settings\.<br />|
|[Parameters](Parameters.md)|This element stores properties about any parameters used with external data connections\. Parameters are used to change the query executed externally and cause different data to be retrieved into the workbook\.The type of parameter used determines whether the user is prompted for a value before data is refreshed, or the value is pulled from a cell in the workbook, or whether the same value should be used until explicitly changed in the data connection\. Parameters are permitted for ODBC and web queries\.<br />|
|[ID](ID.md)|Specifies The unique identifier of this connection\.<br />|
|[SourceFile](SourceFile.md)|Used when the external data source is file\-based\. When a connection to such a data source fails, the spreadsheet application attempts to connect directly to this file\. Can be expressed in URI or system\-specific file path notation\.<br />|
|[OdcFile](OdcFile.md)|Specifies the full path to external connection file from which this connection was created\. If a connection fails during an attempt to refresh data, and ReconnectionMethod is AsRequired, then the spreadsheet application will try again using information from the external connection file instead of the connection object embedded within the workbook\.<br />|
|[KeepAlive](KeepAlive.md)|True when the spreadsheet application should make efforts to keep the connection open\.When false, the application should close the connection after retrieving the information\.<br />|
|[Interval](Interval.md)|Specifies the number of minutes between automatic refreshes of the connection\. When this attribute is not present, the connection is not automatically refreshed\.<br />|
|[Name](Name.md)|Specifies the name of the connection\. Each connection shall have a unique name\.<br />|
|[Description](Description.md)|Specifies the user description for this connection\.<br />|
|[ConnectionType](ConnectionType.md)|Specifies the data source type\.<br />|
|[ReconnectionMethod](ReconnectionMethod.md)|Specifies what the spreadsheet application should do when a connection fails\.<br />|
|[RefreshedVersion](RefreshedVersion.md)|For backward compatibility purposes, this attribute indicates the version of the spreadsheet application that last refreshed the connection\.<br />|
|[MinRefreshable&#8203;Version](MinRefreshableVersion.md)|For compatibility with legacy spreadsheet applications\. This represents the minimum version \# that is required to be able to correctly refresh the data connection\.<br />|
|[SavePassword](SavePassword.md)|True if the password is to be saved as part of the connection string|
|[IsNew](IsNew.md)|True if the connection has not been refreshed for the first time\. This can happen when the user saves the file before a query has finished returning\.<br />|
|[Deleted](Deleted.md)|Indicates whether the associated workbook connection has been deleted\.<br />Deleted connections contain only the attributes name and deleted=true, all other information is removed when saving the file\.<br />If a new connection is created with the same name as a deleted connection, then the deleted connection is overwritten by the new connection\.<br />|
|[OnlyUseConnection&#8203;File](OnlyUseConnectionFile.md)|Indicates whether the spreadsheet application should always and only use the connection information in the external connection file indicated by the odcFile attribute when the connection is refreshed\.<br />If false, then the spreadsheet application should follow the procedure indicated by the reconnectionMethod attribute\.<br /><br />Applies to ODBC connections, and may be applied to custom data connections\.This attribute is ignored for other types of connections\.<br />|
|[SingleSignOnId](SingleSignOnId.md)|Identifier for Single Sign On \(SSO\) used for authentication between an intermediate spreadsheetML server and the external data source\.<br />|
|[Credentials](Credentials.md)|Specifies the authentication method to be used when establishing \(or re\-establishing\) the connection\.<br />|
|[SaveData](SaveData.md)|True if the external data fetched over the connection to populate a table is to be saved with the workbook; otherwise, false\.<br />This exists for data security purposes \- if no external data is saved in \(or "cached"\) in the workbook, then current user credentials can be required every time to retrieve the relevant data, and people won't see the data the workbook author had last been using before saving the file\.<br />|
|[RefreshOnLoad](RefreshOnLoad.md)|True if this connection should be refreshed when opening the file\.<br />|
|[Background](Background.md)|Indicates whether the connection can be refreshed in the background \(&#8203;asynchronously\)&#8203;\.&#8203;<br />True if preferred usage of the connection is to refresh asynchronously in the background; False if preferred usage of the connection is to refresh synchronously in the foreground\.<br />|



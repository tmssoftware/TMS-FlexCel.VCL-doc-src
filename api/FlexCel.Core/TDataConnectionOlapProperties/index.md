---
uid: TDataConnectionOlapProperties
description: TDataConnectionOlapProperties
---

# TDataConnectionOlapProperties Class

This element contains all the properties needed for an OLAP data connection\. OLAP connections contain both the [TDataConnectionDbProperties](../TDataConnectionDbProperties/index.md) and TDataConnectionOlapProperties child elements\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionOlapProperties = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Local](Local.md)|Flag indicating whether we should get data from the local cube on refresh versus the original data source\. true if a local cube has been created for OLAP data, and it should be used instead of the server\.<br />|
|[LocalConnection](LocalConnection.md)|Specifies a connection string to use when a local cube is available\. This is used when local is set to true\.<br />|
|[LocalRefresh](LocalRefresh.md)|Flag indicating whether we should refresh the local cube from the original data source\.<br />When true, the original OLAP data source is queried each time the user explicitly refreshes the data in the application, and a new local cube is constructed from this query\.<br />|
|[SendLocale](SendLocale.md)|When true, the spreadsheetML app should send the user interface locale ID to the OLAP provider to retrieve localized member names and properties, etc\. When false, no locale ID is expected\.<br />|
|[RowDrillCount](RowDrillCount.md)|Maximum number of drill\-through rows to return when the user drills through an aggregate value in a PivotTable\.<br />|
|[ServerFill](ServerFill.md)|When true a PivotTable based on an OLAP source should format the data and aggregate cells in the PivotTable view using the background color from the OLAP source if this information is available\.When false, OLAP server background fill colors are ignored, and standard formatting rules within the worksheet are followed\.<br />|
|[ServerNumberFormat](ServerNumberFormat.md)|When true, a PivotTable based on OLAP source should format the data and aggregate cells in the PivotTable view using the number format from the OLAP source\.When false, OLAP server number formats are ignored, and standard formatting rules within the worksheet are followed\.<br />|
|[ServerFont](ServerFont.md)|When true, a PivotTable based on OLAP source should format the data and aggregate cells in the PivotTable view using the font from the OLAP source \(e\.g\., Arial or Tahoma\)\.<br />When false, OLAP server fonts are ignored, and standard formatting rules within the worksheet are followed\.<br />|
|[ServerFontColor](ServerFontColor.md)|When true a PivotTable based on OLAP source should format the data and aggregate cells in the PivotTable view using the font color from the OLAP source\.When false, OLAP server font colors are ignored, and standard formatting rules within the worksheet are followed\.<br />|



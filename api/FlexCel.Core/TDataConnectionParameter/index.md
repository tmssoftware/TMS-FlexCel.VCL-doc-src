---
uid: TDataConnectionParameter
description: TDataConnectionParameter
---

# TDataConnectionParameter Class

This element stores properties about any parameters used with external data connections\. Parameters are used to change the query executed externally and cause different data to be retrieved into the workbook\.The type of parameter used determines whether the user is prompted for a value before data is refreshed, or the value is pulled from a cell in the workbook, or whether the same value should be used until explicitly changed in the data connection\. Parameters are permitted for ODBC and web queries\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataConnectionParameter = class(TFlexCelObject);</code></pre>

## Methods

|Name|Description|
|---|---|
|[Equals](Equals.md)|Returns true if both objects are the same\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|The name of the parameter\.<br />|
|[SqlType](SqlType.md)|SQL data type of the parameter\. This attribute is only supported for ODBC data sources\.<br />For more information, including supported data types, see ISO 9075\-3:2008, Table 33 \- Codes used for concise data types\.<br />|
|[ParameterType](ParameterType.md)|Type of parameter used\. If the parameterType=value, then the value from [AsBoolean](AsBoolean.md), [AsDouble](AsDouble.md), [AsInteger](AsInteger.md), or [AsString](AsString.md) are used\.In this case, it is expected that only one of  those properties is specified\.<br />|
|[RefreshOnChange](RefreshOnChange.md)|Flag indicating whether the query should automatically refresh when the contents of a cell that provides the parameter value changes\. If true, then external data is refreshed using the new parameter value every time there's a change\. If false, then external data is only refreshed when requested by the user, or some other event triggers refresh \(e\.g\., workbook opened\)\.<br />|
|[Prompt](Prompt.md)|Prompt string for the parameter\. Presented to the spreadsheet user along with input UI to collect the parameter value before refreshing the external data\.Used only when [ParameterType](ParameterType.md) = prompt\.<br />|
|[AsBoolean](AsBoolean.md)|Boolean value to use as the query parameter\. Used only when [ParameterType](ParameterType.md) = value\.<br />|
|[AsDouble](AsDouble.md)|Non\-integer numeric value to use as the query parameter\. Used only when [ParameterType](ParameterType.md)  = value\.<br />|
|[AsInteger](AsInteger.md)|Integer value to use as the query parameter\. Used when [ParameterType](ParameterType.md) = value\.<br />|
|[AsString](AsString.md)|String value to use as the query parameter\. Used only when [ParameterType](ParameterType.md) = value\.<br />|
|[AsCell](AsCell.md)|Cell reference indicating which cell's value to use for the query parameter\. Used only when [ParameterType](ParameterType.md) = cell\.<br />|



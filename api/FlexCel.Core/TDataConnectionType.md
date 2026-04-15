---
uid: TDataConnectionType
description: TDataConnectionType
---

# TDataConnectionType Enumeration

Represents a connection type\. This enumeration lists the documented values, but there could be other values peresent in the file\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Unknown|0|Invalid value\. This value shouldn't happen on a file\.<br />|
|ODBC|1|ODBC\-based source\.<br />|
|CustomDAO|2|Custom data connection source\. This value is application\-defined, but in Office it is used for DAO connections\.<br />|
|CustomApplicationDefined|3|Custom data connection source\. This value is application\-defined, but in Office it is used for application defined connection files\.<br />|
|WebQuery|4|A Web Query\.<br />|
|CustomOLEDB|5|Custom data connection source\. This value is application\-defined, but in Office it is used for OLEDB connections\.<br />|
|Text|6|Text\-based source\.<br />|
|CustomADO|7|Custom data connection source\. This value is application\-defined, but in Office it is used for ADO connections\.<br />|
|CustomDSP|8|Custom data connection source\. This value is application\-defined, but in Office it is used for DSP connections\.<br />|



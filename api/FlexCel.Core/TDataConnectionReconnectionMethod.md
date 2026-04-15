---
uid: TDataConnectionReconnectionMethod
description: TDataConnectionReconnectionMethod
---

# TDataConnectionReconnectionMethod Enumeration

How to reconnect when a connection fails\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Unknown|0|Invalid value\. This value shouldn't happen on a file\.<br />|
|AsRequired|1|On refresh use the existing connection information\. If the existing information cannot be used to establish a connection, get updated connection information, if available from the external connection file\.<br />|
|Always|2|On every refresh get updated connection information from the external connection file, if available, and use that instead of the existing connection information\.<br />In this case the data refresh will fail if the external connection file is unavailable\.<br />|
|Never|3|Never get updated connection information from the external connection file even if it is available and even if the existing connection information cannot be used\.<br />|



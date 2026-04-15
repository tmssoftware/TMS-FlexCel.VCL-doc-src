---
uid: TDisposeMode
description: TDisposeMode
---

# TDisposeMode Enumeration

Indicates if FlexCel must dispose a table after it is done using it\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|DoNotDispose|0|FlexCel will not dispose the table\. Use this option for example when adding a table that was created on the designer\.<br />|
|DisposeAfterRun|1|FlexCel will dispose this table after it has finish using it\. Use this option when adding temporary datasets, so you do not have to take care of disposing the table yourself\.<br />|



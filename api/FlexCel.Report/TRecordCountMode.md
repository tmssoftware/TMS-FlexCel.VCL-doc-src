---
uid: TRecordCountMode
description: TRecordCountMode
---

# TRecordCountMode Enumeration

Sets the way FlexCel will count the records\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Normal|0|FlexCel will try to use a field named \_\_FLEXCELCOUNT, and if not available, it will use TDataSet\.RecordCount\.<br />|
|SlowCount|1|FlexCel will count the records by fetching them all\.<br />|



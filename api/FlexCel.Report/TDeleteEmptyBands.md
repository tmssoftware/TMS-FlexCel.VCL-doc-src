---
uid: TDeleteEmptyBands
description: TDeleteEmptyBands
---

# TDeleteEmptyBands Enumeration

Defines how bands will be removed when they have 0 records\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|MoveRangeUp|0|All the sheet will be moved up, and the rows of the band will disappear\.<br />|
|ClearDataOnly|1|The cells in the sheet won't move, but the data in the cells will be cleared\. Formats of the cell will remain\.<br />|
|ClearDataAndFormats|2|The cells in the sheet won't move, but all data and formats in the cells will be cleared\.<br />|



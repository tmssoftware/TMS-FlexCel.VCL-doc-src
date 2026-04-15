---
uid: TFlxInsertMode
description: TFlxInsertMode
---

# TFlxInsertMode Enumeration

Inserting mode\. **Important:** This enumeration is also used when deleting ranges\. When deleting, Down means Up and Right means Left\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|NoneDown|0|Cells will not be inserted but just overwrite existing ones\. If count is >0, additional ranges will be copied down\.<br /><br />When deleting, this mode will clear the cells and not move anything\.<br />|
|NoneRight|1|Cells will not be inserted but just overwrite existing ones\. If count is >0, additional ranges will be copied right\.<br /><br />When deleting, this mode will clear the cells and not move anything\.<br />|
|ShiftRowDown|2|Inserts whole rows\. Moves all destination rows down\.<br /><br />When deleting, moves cells up\.<br />|
|ShiftColRight|3|Inserts whole columns\. Moves all destination columns to the right\.<br /><br />When deleting, moves columns to the right of the deleted columns to the left\.<br />|
|ShiftRangeDown|4|Moves all destination cells down\. This WON'T move the whole row, only cells on the range\.<br /><br />When deleting, moves cells up\.<br />|
|ShiftRangeRight|5|Moves all destination cells to the right\. This WON'T move the whole column, only cells on the range\.<br /><br />When deleting, moves cells to the left\.<br />|



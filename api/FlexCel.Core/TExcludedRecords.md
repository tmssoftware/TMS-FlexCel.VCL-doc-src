---
uid: TExcludedRecords
description: TExcludedRecords
---

# TExcludedRecords Enumeration

A list of records that might not be saved into a file when using [TExcelFile.SaveForHashing\(TStream\)](TExcelFile/SaveForHashing.md#texcelfilesaveforhashingtstream)

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|WriteAccess|0|This is a stamp that is saved to the file each time it is saved, identifying the current user\. You normally won't want to save this record, so you should specify this value\.<br />|
|CellSelection|1|If you specify CellSelection, the selected cells will be ignored\.<br />|
|SheetSelected|2|If you specify SheetSelected, the active sheet will be ignored\.<br />|
|Version|3|If you specify Version, the version of Excel used to save the file will be ignored\. \(Note that version might change in an Excel Service Pack\)\.<br />|



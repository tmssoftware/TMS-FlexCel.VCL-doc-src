---
uid: TFlexCelReportProgressPhase
description: TFlexCelReportProgressPhase
---

# TFlexCelReportProgressPhase Enumeration

Phase of the report we are in\.


## Syntax

**Unit:** [FlexCel.Report](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|NotRunning|0|Report is inactive\.<br />|
|ReadTemplate|1|Reading and parsing the template\.<br />|
|OrganizeData|2|Organizing the data on the template\.<br />|
|CopyStructure|3|Inserting the needed rows/ranges for the report\.<br />|
|FillData|4|Replacing the tags with the new values\.<br />|
|FinalCleanup|5|Fixing pagebreak or delete rows tags\.<br />|
|Done|6|Report has finished\.<br />|



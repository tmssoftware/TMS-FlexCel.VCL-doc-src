---
uid: TDataValidationIcon
description: TDataValidationIcon
---

# TDataValidationIcon Enumeration

Icon to be displayed in the error box of a data validation action\. Note that this not only affects the icon used, but the possible values\.
An information icon will allow you to enter an invalid value in a cell, a stop icon will not\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Stop|0|Stop icon\.  \( a red circle with a cross\)\. When selected, invalid values cannot be entered into the cell\.<br />|
|Warning|1|Warning icon\. \( a yellow triangle with an exclamation sign\)\. When selected and there is an invalid entry, you get an error dialog allowing to cancel the operation, enter the invalid value anyway or re edit the cell\.<br />|
|Information|2|Information icon\. \(a text ballon with an "i" inside\)\. When selected and there is an invalid entry, a waning will be shown but the invalid data can be entered anyway\.<br />|



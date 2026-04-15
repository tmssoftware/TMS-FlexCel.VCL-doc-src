---
uid: TCondFmtError
description: TCondFmtError
---

# TCondFmtError Enumeration

Errors that might happen in a conditional format\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|NoError|0|No error was found\.<br />|
|NullRange|1|There are no ranges\.<br />|
|NullRules|2|There are no rules\.<br />|
|TopLessThan0|3|One range has a Top less than 0;|
|BottomMoreThanMax|4|One range has bottom bigger than the maximum rows allowed in a sheet\.<br />|
|BottomLessThanTop|5|One range has the top bigger than the bottom\.<br />|
|LeftLessThan0|6|One range has a Left less than 0;|
|RightMoreThanMax|7|One range has right bigger than the maximum columns allowed in a sheet\.<br />|
|RightLessThanLeft|8|One range has the left bigger than the right\.<br />|
|PriorityMustBeBiggerThanZero|9|Priority must be bigger than 0\.<br />|
|IconSetMustHaveIconCountLess1Values|10|An iconset must have a list of values with a count of the number of icons \-1\. So if the iconset has 3 icons, the values must be 2\.<br />|
|IconSetCantBeNone|11|You can't specify an iconset of none\. An iconset of none can only be used in custom icons\.<br />|
|ColorScalesMustHaveAtLeast2Values|12|A color scale must have at least 2 values\.<br />|
|ColorScalesMustHaveTheSameNumberOfValuesAndColors|13|The number of colors in the color scale must be the same as the number of values\.<br />|



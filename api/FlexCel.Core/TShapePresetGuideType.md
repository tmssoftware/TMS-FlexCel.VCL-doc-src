---
uid: TShapePresetGuideType
description: TShapePresetGuideType
---

# TShapePresetGuideType Enumeration

Internal use\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Pr\_cd|0|m/n of a Circle \('mcdn'\) \-  The units here are in 60,000ths of a degree\.<br />|
|Pr\_b|1|Shape Bottom Edge \('b'\) \- Constant value of "h"  This is the bottom edge of the shape and since the top edge of the shape is considered the 0 point, the bottom edge is thus the shape height\.<br />|
|Pr\_h|2|Shape Height \('h'\)  This is the variable height of the shape defined in the shape properties\. This value is received from the shape transform listed within the spPr element\.<br />|
|Pr\_hc|3|Horizontal Center \('hc'\) \- Calculated value of "\*/ w 1\.0 2\.0"  This is the horizontal center of the shape which is just the width divided by 2\.<br />|
|Pr\_hd|4|1/n of Shape Height \('hdn'\) \- Calculated value of "\*/ h 1\.0 n\.0"  This is 1/n the shape height\.<br />|
|Pr\_l|5|Shape Left Edge \('l'\) \- Constant value of "0"  This is the left edge of the shape and the left edge of the shape is considered the horizontal 0 point\.<br />|
|Pr\_ls|6|Longest Side of Shape \('ls'\) \- Calculated value of "max w h"  This is the longest side of the shape\. This value is either the width or the height depending on which is greater\.<br />|
|Pr\_r|7|Shape Right Edge \('r'\) \- Constant value of "w"  This is the right edge of the shape and since the left edge of the shape is considered the 0 point, the right edge is thus the shape width\.<br />|
|Pr\_ss|8|Shortest Side of Shape \('ss'\) \- Calculated value of "min w h"  This is the shortest side of the shape\. This value is either the width or the height depending on which is smaller\.<br />|
|Pr\_ssd|9|1/n Shortest Side of Shape \('ssdn'\) \- Calculated value of "\*/ ss 1\.0 n\.0"|
|Pr\_t|10|Shape Top Edge \('t'\) \- Constant value of "0"  This is the top edge of the shape and the top edge of the shape is considered the vertical 0 point\.<br />|
|Pr\_vc|11|Vertical Center of Shape \('vc'\) \- Calculated value of "\*/ h 1\.0 2\.0"  This is the vertical center of the shape which is just the height divided by 2\.<br />|
|Pr\_w|12|Shape Width \('w'\)  This is the variable width of the shape defined in the shape properties\. This value is received from the shape transform listed within the spPr element\.<br />|
|Pr\_wd|13|1/n of Shape Width \('wdn'\) \- Calculated value of "\*/ w 1\.0 n\.0" This is 1/n the shape width\.<br />|



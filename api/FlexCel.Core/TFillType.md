---
uid: TFillType
description: TFillType
---

# TFillType Enumeration

Type of fill for an autoshape\. \(In xls files\)

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Solid|0|Fill with a solid color|
|Pattern|1|Fill with a pattern \(bitmap\)|
|Texture|2|A texture \(pattern with its own color map\)|
|Picture|3|Center a picture in the shape|
|Shade|4|Shade from start to end points|
|ShadeCenter|5|Shade from bounding rectangle to end point|
|ShadeShape|6|Shade from shape outline to end point|
|ShadeScale|7|Similar to msofillShade, but the fillAngle is additionally scaled by the aspect ratio of the shape\. If shape is square, it is the same as msofillShade\.<br />|
|ShadeTitle|8|special type \- shade to title \-\-\-  for PP|
|Background|9|the background fill color/pattern|



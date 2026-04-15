---
uid: TTextVertOverflow
description: TTextVertOverflow
---

# TTextVertOverflow Enumeration

How the text in a shape will overflow vertically once there is no more room for it\.
Note that from the Excel UI, you can only set both Vert overflow and Horizontal overflow at the same time\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Overflow|0|Text will not be clipped, and it will overflow outside the shape\.<br />|
|Clip|1|Text will be clipped, and there will be no indication that there is more text outside the area\.<br />|
|Ellipsis|2|Text will be clipped, but there will be an ellipsis to indicate that the text continues after the clip\.<br />|



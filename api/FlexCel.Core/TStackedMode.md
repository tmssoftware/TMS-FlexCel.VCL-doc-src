---
uid: TStackedMode
description: TStackedMode
---

# TStackedMode Enumeration

Way the series stack one to the other\. This does not apply to all chart types\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Standard|0|Data is not Stacked\. Each series is drawn after the other along the z\-axis\.<br />|
|Clustered|1|Data is not Stacked\. Each series is drawn after the other along the x/y\-axis\. If only applies to bar or column charts, where each bar is drawn one after the other around the axis\. A 3D bar chart can be either standard \(where each bar is drawn along the z axis\), or Clustered \(where each bar is drawn along the x axis\)\.<br />|
|Stacked|2|Data is Stacked\. \(for example in stacked bar chart\)|
|Stacked100|3|Data is stacked and normalized to 100%%\. \(This is a 100%% stacked bar/column chart\)|



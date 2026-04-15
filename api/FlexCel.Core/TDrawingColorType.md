---
uid: TDrawingColorType
description: TDrawingColorType
---

# TDrawingColorType Enumeration

Defines the kind of colors that might be stored inside a color definition in a drawing or a theme\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|HSL|0|Hue, Saturation, Luminance\.<br />|
|Preset|1|Color is from the list in [TPresetColor](TPresetColor.md)\.<br />|
|RGB|2|RGB expressed as components\. Components are in the range 0\-255|
|scRGB|3|scRGB color mode\. Components are in the range 0\-1\.<br />|
|System|4|System color\. This is defined by windows, for example the color of the active caption\.<br />|
|Theme|5|Links to a theme color\. You can't use this value when defining the theme colors themselves\.<br />|



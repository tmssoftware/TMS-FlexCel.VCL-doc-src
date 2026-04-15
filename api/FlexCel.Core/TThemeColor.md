---
uid: TThemeColor
description: TThemeColor
---

# TThemeColor Enumeration

Specifies one of the 12 theme colors, or one of the 4 semantic colors\. In cells, Excel doesn't use semantic colors, but in drawings they can be used, even if the Excel UI only allows one type of color\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|-1|No theme color\.<br />|
|Light1|0|Main color for backgrounds in Theme\. **Normally it is better to use the semantic variation of this theme: Background1**\.<br />|
|Dark1|1|Main color for foregrounds in Theme\. **Normally it is better to use the semantic variation of this theme: Foreground1**\.<br />|
|Light2|2|Secondary color for backgrounds in Theme\. **Normally it is better to use the semantic variation of this theme: Background2**\.<br />|
|Dark2|3|Secondary color for foregrounds in Theme\.  **Normally it is better to use the semantic variation of this theme: Foreground2**\.<br />|
|Accent1|4|Accent1 Theme\.<br />|
|Accent2|5|Accent2 Theme\.<br />|
|Accent3|6|Accent3 Theme\.<br />|
|Accent4|7|Accent4 Theme\.<br />|
|Accent5|8|Accent5 Theme\.<br />|
|Accent6|9|Accent6 Theme\.<br />|
|HyperLink|10|HyperLink Theme\.<br />|
|FollowedHyperLink|11|FollowedHyperLink Theme\.<br />|
|Background1|256|Primary semantic color for the background\.<br />This color isn't a real theme color and normally it is mapped to Light1\.<br />In cells it doesn't matter what you use: Background1 or Light1 as both are mapped internally to Light1\.<br />But in drawings Excel allows both types of themes even if they normally are the same\.<br />|
|Foreground1|257|Primary semantic color for the foreground\.<br />This color isn't a real theme color and normally it is mapped to Dark1\.<br />In cells it doesn't matter what you use: Forground1 or Dark1 as both are mapped internally to Dark1\.<br />But in drawings Excel allows both types of themes even if they normally are the same\.<br />|
|Background2|258|Secondary semantic color for the background\.<br />This color isn't a real theme color and normally it is mapped to Light2\.<br />In cells it doesn't matter what you use: Background2 or Light2 as both are mapped internally to Light2\.<br />But in drawings Excel allows both types of themes even if they normally are the same\.<br />|
|Foreground2|259|Secondary semantic color for the foreground\.<br />This color isn't a real theme color and normally it is mapped to Dark2\.<br />In cells it doesn't matter what you use: Forground2 or Dark2 as both are mapped internally to Dark2\.<br />But in drawings Excel allows both types of themes even if they normally are the same\.<br />|



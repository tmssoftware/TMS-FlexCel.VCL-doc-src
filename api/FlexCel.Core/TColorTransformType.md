---
uid: TColorTransformType
description: TColorTransformType
---

# TColorTransformType Enumeration

List of transformations that can be done to a color\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Tint|0|Yields a lighter version of its input color\. A 10%% tint is 10%% of the input color combined with 90%% white\.<br />|
|Shade|1|Yields a darker version of its input color\. A 10%% shade is 10%% of the input color combined with 90%% black\.<br />|
|Complement|2|Yields the complement of its input color\. For example, the complement of red is green\.<br />|
|Inverse|3|Yields the inverse of its input color\. For example, the inverse of red \(1,0,0\) is cyan \(0,1,1\)\.<br />|
|Gray|4|Yields a grayscale of its input color, taking into relative intensities of the red, green, and blue primaries\.<br />|
|Alpha|5|Yields its input color with the specified opacity, but with its color unchanged\.<br />|
|AlphaOff|6|Yields a more or less opaque version of its input color\. An alpha offset never increases the alpha beyond 100%% or decreases below 0%%; i\.e\., the result of the transform pins the alpha to the range of \[0%%,100%%\]\. A 10%% alpha offset increases a 50%% opacity to 60%%\. A \-10%% alpha offset decreases a 50%% opacity to 40%%\.<br />|
|AlphaMod|7|Yields a more or less opaque version of its input color\. An alpha modulate never increases the alpha beyond 100%%\. A 200%% alpha modulate makes a input color twice as opaque as before\. A 50%% alpha modulate makes a input color half as opaque as before\.<br />|
|Hue|8|Yields the input color with the specified hue, but with its saturation and luminance unchanged\.<br />|
|HueOff|9|Yields the input color with its hue shifted, but with its saturation and luminance unchanged\.<br />|
|HueMod|10|Yields the input color with its hue modulated by the given percentage\.<br />|
|Sat|11|Yields the input color with the specified saturation, but with its hue and luminance unchanged\. Typically saturation values fall in the range \[0%%, 100%%\]\.<br />|
|SatOff|12|Yields the input color with its saturation shifted, but with its hue and luminance unchanged\.<br />|
|SatMod|13|Yields the input color with its saturation modulated by the given percentage\. A 50%% saturation modulate reduces the saturation by half\. A 200%% saturation modulate doubles the saturation\.<br />|
|Lum|14|Yields the input color with the specified luminance, but with its hue and saturation unchanged\. Typically, luminance values fall in the range \[0%%,100%%\]\.<br />|
|LumOff|15|Yields the input color with its luminance shifted, but with its hue and saturation unchanged\.<br />|
|LumMod|16|Yields the input color with its luminance modulated by the given percentage\. A 50%% luminance modulate reduces the luminance by half\. A 200%% luminance modulate doubles the luminance\.<br />|
|Red|17|Yields the input color with the specified red component, but with its green and blue components unchanged\.<br />|
|RedOff|18|Yields the input color with its red component shifted, but with its green and blue components unchanged\.<br />|
|RedMod|19|Yields the input color with its red component modulated by the given percentage\. A 50%% red modulate reduces the red component by half\. A 200%% red modulate doubles the red component\.<br />|
|Green|20|Yields the input color with the specified green component, but with its red and blue components unchanged\.<br />|
|GreenOff|21|Yields the input color with its green component shifted, but with its red and blue components unchanged\.<br />|
|GreenMod|22|Yields the input color with its green component modulated by the given percentage\. A 50%% green modulate reduces the green component by half\. A 200%% green modulate doubles the green component\.<br />|
|Blue|23|Yields the input color with the specified blue component, but with its red and green components unchanged\.<br />|
|BlueOff|24|Yields the input color with its blue component shifted, but with its red and green components unchanged\.<br />|
|BlueMod|25|Yields the input color with its blue component modulated by the given percentage\. A 50%% blue modulate reduces the blue component by half\. A 200%% blue modulate doubles the blue component\.<br />|
|Gamma|26|Yields the sRGB gamma shift of its input color\.<br />|
|InvGamma|27|Yields the inverse sRGB gamma shift of its input color\.<br />|



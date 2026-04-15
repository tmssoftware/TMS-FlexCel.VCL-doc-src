---
uid: TFontScheme
description: TFontScheme
---

# TFontScheme Enumeration

Specifies the scheme to which a font belongs in the theme\. This attribute is only valid in Excel 2007 or newer\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|Font is not a theme font and is not linked to the theme\. When you change the  theme of the spreadsheet, "None" fonts will remain unchanged\.<br />|
|Minor|1|The font is a minor font for the scheme\. This is the font that shows **\(Body\)** at the right of the font selector box in Excel\. Whenever you change the theme of the spreadsheet, all minor fonts in all cells will change to reflect the new minor font in the theme\.<br />|
|Major|2|The font is a major font for the scheme\. This is the font that shows **\(Headings\)** at the right of the font selector box in Excel\. Whenever you change the theme of the spreadsheet, all major fonts in all cells will change to reflect the new major font in the theme\.<br />|



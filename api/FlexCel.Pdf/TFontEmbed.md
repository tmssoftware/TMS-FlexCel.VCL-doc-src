---
uid: TFontEmbed
description: TFontEmbed
---

# TFontEmbed Enumeration

The way fonts will be embedded on the resulting pdf file\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|No font will be embedded\. The result file will be smaller, but the file might not look fine on a computer without the font installed\. It is recommended that you embed the fonts\.<br />|
|Embed|1|All fonts will be embedded\. The file will be larger than when not embedding fonts, but it will print on any computer\.<br />Note that you can control which fonts to embed and which not with the OnFontEmbed event\.<br />|
|OnlySymbolFonts|2|This is a compromise between embedding all fonts and not embedding them\. It will only embed fonts with symbols, and leave normal fonts not embedded\.<br />|



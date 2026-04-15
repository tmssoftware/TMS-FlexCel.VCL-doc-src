---
uid: TFontMapping
description: TFontMapping
---

# TFontMapping Enumeration

How fonts will be replaced on the generated PDF file\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ReplaceStandardFonts|0|Arial will be replaced with Helvetica, Times new roman with Times and True type Courier with PS1 Courier\. All other fonts will remain unchanged\.<br />|
|ReplaceAllFonts|1|Serif fonts will be mapped to Times, MonoSpace to Courier, Sans\-Serif to Helvetica and Symbol fonts to Symbol\. Using this option you can get the smallest file sizes and 100%% portability, but the resulting file will only use those fonts\. Use it with care, specially if you use symbol fonts\.<br />|
|DontReplaceFonts|2|All actual fonts will be used\. If you use this option and do not embed fonts, the fonts will look bad on computers without them installed\. If you embed fonts, files will be larger\.<br />|



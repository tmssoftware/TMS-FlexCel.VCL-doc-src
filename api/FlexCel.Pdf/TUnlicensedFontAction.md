---
uid: TUnlicensedFontAction
description: TUnlicensedFontAction
---

# TUnlicensedFontAction Enumeration

Determines what to do when trying to embed a font that isn't licensed for embedding\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Error|0|If the font doesn't have a valid license, FlexCel will throw an exception and won't complete the exporting\.<br />|
|Replace|1|If the font doesn't have a valid license, FlexCel will replace it by the font specified in the UnlicensedFontReplacement property\.<br />|
|Ignore|2|FlexCel won't look at the licensing of the font, and embed it anyway\. Note that to use this option, you need to have a copyright agreement to distribute the font with its owner\. Also note that in PDF/A mode this option is similar to Error and an Exception will be thrown\. This is because PDF/A doesn't allow to embed fonts which don't have the correct license, and the document wouldn't validate\.<br />|



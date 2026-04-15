---
uid: TFontSubset
description: TFontSubset
---

# TFontSubset Enumeration

Determines if full fonts will be embedded in the generated pdf files, or only the characters being used\.


## Syntax

**Unit:** [FlexCel.Pdf](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|DontSubset|0|All characters of the font will be embedded into the file\. This setting creates bigger files, but they can be edited after generated\.<br />|
|Subset|1|Only characters actually used by the document will be embedded into the file\. This will create smaller files than  embedding the full font, but it will be difficult to edit the document once it has been created\.<br />|



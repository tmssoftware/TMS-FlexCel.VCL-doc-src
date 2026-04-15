---
uid: TRangeCopyMode
description: TRangeCopyMode
---

# TRangeCopyMode Enumeration

What we do with the cells when we call InsertAndCopyRange\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|All|0|Will copy all \(values, ranges, images, formulas, etc\)\.<br />|
|OnlyFormulas|1|Will copy all except values\. Useful when you are going to replace those values anyway\.<br />|
|None|2|Won't copy anything\. Only inserts\.<br />|
|OnlyFormulasAndNoObjects|3|Will copy all except values and objects \(like images\)\. Useful when you are going to replace those values anyway\.<br />|
|AllIncludingDontMoveAndSizeObjects|4|Will copy all objects, including those that are marked as "do not copy" in the file\. You will normally not want to use this\.<br />|
|Formats|5|Will copy cell formatting, but not cell contents\. Images and objects will be copied too\.<br />|



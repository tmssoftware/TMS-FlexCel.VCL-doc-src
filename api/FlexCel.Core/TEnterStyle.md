---
uid: TEnterStyle
description: TEnterStyle
---

# TEnterStyle Enumeration

Defines how characters will be converted when encoding a string as Html\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Br|0|Enter characters in the input string will be converted to<br />tags\. Multiple spaces will be converted to &amp;nbsp; entities\.<br />|
|Char10|1|Enter characters in the input string will be converted to &amp;\#0A; entities\. Multiple spaces will be not converted\.<br />|
|Ignore|2|Enter and multiple spaces will be ignored\.<br />|
|Legacy2003Xml|3|This is a "pseudo xml" that is used to write the object texts\. No entities more than the ones allowed in xml are used, breaks are<br />and multiple spaces are the actual char 160, instead of &amp;nbsp; which isn't allowed in xml\.<br />|
|IgnoreBreaksButKeepSpaces|4|Enter will be ignored and spaces will be converted to nbsp\.<br />|



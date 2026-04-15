---
uid: TFlxFontStyles
description: TFlxFontStyles
---

# TFlxFontStyles Enumeration

Font style\. You can "or" on "and" it to get the actual styles\.
For example, to set style to bold\+italic,  you should use TFlxFontStyles\.Bold \| TFlxFontStyles\.Italic\.
to check if style includes italic, use \(\(Style &amp; TFlxFontStyles\.Italic\)\!=0\)

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Bold|0|Bold font\.|
|Italic|1|Italic font\.|
|StrikeOut|2|Stroke out font\.|
|Superscript|3|Superscript font\.|
|Subscript|4|Subscript font\.|
|Outline|5|Outlined font\. Excel currently ignores this setting\.|
|Shadow|6|Font has a shadow\. Excel currently ignores this setting\.|
|Condense|7|Condensed font, for backwards compatibility\. Excel ignores this setting\.<br />|
|Extend|8|Extended font, for backwards compatibility\. Excel ignores this setting\.<br />|



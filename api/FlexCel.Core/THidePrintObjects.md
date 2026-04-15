---
uid: THidePrintObjects
description: THidePrintObjects
---

# THidePrintObjects Enumeration

Enumeration defining which objects should not be printed or exported to PDF\. You can 'or' more than one option together\.
For example, to not print images and not comments, you should specify: THidePrintObjects\.Images \| THidePrintOption\.Comments

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Images|0|Do not print or export images to pdf\.<br />|
|Comments|1|Do not export Comments to pdf\. Note that if the Excel file is configured to print "Comments as displayed" then those comments will be exported as images even if this option is false\. Use THidePrintObjects\.Images to control those comments, as they are considered images\. Or just set [TExcelFile.PrintComments](TExcelFile/PrintComments.md) to be something different than "Comments as displayed"\.<br />|
|Hyperlynks|2|Do not export Hyperlinks to pdf\.<br />|
|Headers|3|Do not print or export to pdf the Headers\.<br />|
|Footers|4|Do not print or export to pdf the Footers\.<br />|
|PageBreaks|5|Do not export page breaks\. This property only applies to html exports\.<br />|



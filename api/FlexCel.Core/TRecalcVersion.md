---
uid: TRecalcVersion
description: TRecalcVersion
---

# TRecalcVersion Enumeration

Identifies how FlexCel will identify itself in the generated file, in order to recalculate\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|AlwaysRecalc|0|If you choose this option, Excel will always recalculate the full file on open, and ask for saving changes when closing the file\.<br />|
|SameAsInputFile|1|FlexCel will write the same information that was in the original file it opened\.<br />Note that if you create a file with XlsFile\.NewFile, then the version will be the  version you specify in the NewFile parameters\. By default, this is Excel 2003\.<br />|
|LatestKnownExcelVersion|2|This will use the latest Excel version that FlexCel is aware of\. Note that when you update FlexCel to a newer version, the recalculating version might change if it adds support for newer Excel versions\.<br />|
|Excel2003|3|The file will be identified as if it was saved by Excel 2003\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2007|4|The file will be identified as if it was saved by Excel 2007\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2010|5|The file will be identified as if it was saved by Excel 2010\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2013|6|The file will be identified as if it was saved by Excel 2013\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2016|7|The file will be identified as if it was saved by Excel 2016\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2019|8|The file will be identified as if it was saved by Excel 2019\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2021|9|The file will be identified as if it was saved by Excel 2021\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|
|Excel2023|10|The file will be identified as if it was saved by Excel 365 after July 2023\. Any newer Excel version opening the file will recalculate the file on open, and ask to save changes when closing\.<br />|



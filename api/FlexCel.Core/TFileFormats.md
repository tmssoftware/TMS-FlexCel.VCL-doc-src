---
uid: TFileFormats
description: TFileFormats
---

# TFileFormats Enumeration

Supported file formats to read and write files\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Automatic|0|Automatically detect the type of the file when opening files\. If used when saving, FlexCel will choose whether to use xls or xlsx depending on the file extension \(when saving to a file\) or the value of [TExcelFile.DefaultFileFormat](TExcelFile/DefaultFileFormat.md) when saving to a stream or when the format can't be determined from the extension\.<br />|
|Xls|1|Excel 97\-2000\-XP\-2003|
|Text|2|Delimiter separated values\. Depending on the delimiter, this can be csv, tab delimited text, etc\.<br />|
|Pxl|3|Pocket Excel 1\.0 or 2\.0|
|Xlsx|4|Excel 2007 standard file format\. Note that this is \*not\* a macro enabled file format\. If you want to save a file with macros, you need to use Xlsm instead\.<br />|
|Xlsm|5|Excel 2007 macro enabled file format\.<br />|



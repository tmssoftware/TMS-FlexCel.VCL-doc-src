---
uid: TExcelFileFormat
description: TExcelFileFormat
---

# TExcelFileFormat Enumeration

Different Excel versions create different empty xls/xlsx files\. For example an empty xls file created by Excel 2003 will have "Arial" as its default font, and one created by Excel 2007 will have "Calibri"\. By default, when you call [TExcelFile.NewFile](TExcelFile/NewFile.md) FlexCel will create a file that is similar to what Excel 2003 would create\. This is fine, but if you want to start for example from an  empty Excel 2007 file, you can do so by calling NewFile\(\) with this enumeration\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|v2003|0|Empty files will be created as if they were created by Excel 2003\. The default font is Arial\.<br />|
|v2007|1|Empty files will be created as if they were created by Excel 2007\. The default font is Calibri\.<br />|
|v2010|2|Empty files will be created as if they were created by Excel 2010\. The default font is Calibri\.<br />|
|v2013|3|Empty files will be created as if they were created by Excel 2013\. The default font is Calibri\.<br />|
|v2016|4|Empty files will be created as if they were created by Excel 2016\. The default font is Calibri\.<br />|
|v2019|5|Empty files will be created as if they were created by Excel 2019\. The default font is Calibri\.<br />|
|v2021|6|Empty files will be created as if they were created by Excel 2021\. The default font is Calibri\.<br />|
|v2023|7|Empty files will be created as if they were created by Excel 365 after July 2023\. The default font is Aptos\.<br />|



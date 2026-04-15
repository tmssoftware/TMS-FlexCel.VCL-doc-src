---
uid: TRecalcMode
description: TRecalcMode
---

# TRecalcMode Enumeration

Sets how the excel file will be recalculated\. Normally FlexCel calculates a file only before saving and when you explicitly call [TExcelFile.Recalc\(Boolean\)](TExcelFile/Recalc.md#texcelfilerecalcboolean)\. With this enum you can change that behavior\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|Smart|0|The file will be recalculated before saving, \*only\* if there are any changes on the file\. This mode is the recommended, because it allows you to open and save a file \(for example to remove a password\) without modifying the formula results\. If you modify any value on the sheet, a recalculation will be  done to get the new values\.<br />|
|Forced|1|The file will \*always\* be recalculated before saving\. Use it if you are loading files that might not be recalculated, to make sure they will\. If you open a not calculated file  on Smart mode and then save it without modifying anything, it will remain not calculated\.<br />|
|Manual|2|The file will \*never\* be recalculated by FlexCel \(Except if you do a forced recalc: XlsFile\.Recalc\(true\)\. All formula results will be set to null and formulas will be modified so Excel recalculates them when you open the file\. If you are only using Excel to open the generated files the result will be the same as with a recalculated file, but if you try to open it with a viewer you won't see the formula results\.<br />You should not need to use manual recalculation\. The only case where it might be useful is if you are setting the formula results yourself and don't want FlexCel to change them when it saves\.<br />|
|OnEveryChange|3|The file will be recalculated each time a value changes on the sheet\. Do not use this mode on normal files, as it can be really slow\!\!  This option could be of use for an interactive viewer\.<br />|



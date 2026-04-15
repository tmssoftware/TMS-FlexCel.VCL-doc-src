---
uid: TSheetOptions
description: TSheetOptions
---

# TSheetOptions Enumeration

General options for a sheet\. In Excel, this settings are located in Tools\->Options\->View in the "Window options" box\.
Most of this options can be set with dedicated methods in [TExcelFile](TExcelFile/index.md), but this type allows to set them all at once, or copy them from other file\. This options apply only to the active sheet\. For options that apply to all the sheets see [TSheetWindowOptions](TSheetWindowOptions.md)

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|None|0|No option is selected\.<br />|
|ShowFormulaText|1|If 1, Excel will show formula text instead of formula results\. This is the same as calling [TExcelFile.ShowFormulaText](TExcelFile/ShowFormulaText.md)|
|ShowGridLines|2|If 0 Excel will hide the gridlines, if 1 it will show them\. This is the same as calling [TExcelFile.ShowGridLines](TExcelFile/ShowGridLines.md)|
|ShowRowAndColumnHeaders|4|if 0 Excel will hide the "A", "B"\.\.\. column headers and "1", "2" \.\.\. row Headers\. This is the same as calling [TExcelFile.ShowGridHeadings](TExcelFile/ShowGridHeadings.md)|
|ZeroValues|16|If 1 Excel will show formulas with result in 0 as 0\. If not, Excel will show formulas that result in 0 as empty\. This is the same as calling [TExcelFile.HideZeroValues](TExcelFile/HideZeroValues.md)|
|AutomaticGridLineColors|32|If 1, the color of gridlines will be gray\. If 0 it will be the color specified at [TExcelFile.GridLinesColor](TExcelFile/GridLinesColor.md)\.<br />Note that calling [TExcelFile.GridLinesColor](TExcelFile/GridLinesColor.md) will automatically set this property to 0\.<br />|
|RightToLeft|64|If 1, the sheet is Right to left\. This is the same as calling [TExcelFile.SheetIsRightToLeft](TExcelFile/SheetIsRightToLeft.md)|
|OutlineSymbols|128|If 1, Excel will show the outline symbols \(\+/\-\) when there are grouped rows or columns\.<br />|
|PageBreakView|2048|If 1 Excel will show the page breaks\.<br />|



---
uid: TFlxConsts
description: TFlxConsts
---

# TFlxConsts Record

Utility methods and constants usable anywhere\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFlxConsts = record;</code></pre>

## Constants

|Name|Description|
|---|---|
|[Max\_Columns97\_2003](Max_Columns97_2003.md)|Maximum column on an xls \(Excel 97 \- 2003\) spreadsheet\. \(0 based, that is 255\)|
|[Max\_Columns2007](Max_Columns2007.md)|Maximum column on an xlsx \(Excel 2007 and up\) spreadsheet\. \(0 based, that is 16383\)|
|[Max\_Rows97\_2003](Max_Rows97_2003.md)|Maximum row on an xls \(Excel 97 \- 2003\) spreadsheet\. \(0 based, that is 65535\)|
|[Max\_Rows95](Max_Rows95.md)|Maximum row on an xls \(Excel 2 \- 95\) spreadsheet\. \(0 based\)|
|[Max\_Rows2007](Max_Rows2007.md)|Maximum row on an xlsx \(Excel 2007 and up\) spreadsheet\. \(0 based, that is 1048575\)|
|[Max\_Sheets](Max_Sheets.md)|Maximum sheet on a spreadsheet\. \(0 based, that is 65530\)|
|[Max\_PxlColumns](Max_PxlColumns.md)|Maximum column on Pocket Excel a spreadsheet\. \(0 based, that is 255\)|
|[Max\_PxlRows](Max_PxlRows.md)|Maximum row on a Pocket Excel spreadsheet\. \(0 based, that is 16383\)|
|[Max\_PxlSheets](Max_PxlSheets.md)|Maximum sheet on a Pocket Excel spreadsheet\. \(0 based, that is 255\)|
|[Max\_&#8203;Formula&#8203;Arguments2003](Max_FormulaArguments2003.md)|Maximum number of arguments for a formula in xls file format\.<br />|
|[Max\_&#8203;Formula&#8203;Arguments2007](Max_FormulaArguments2007.md)|Maximum number of arguments for a formula in xlsx file format\.<br />|
|[Max\_StringLenInCell](Max_StringLenInCell.md)|Maximum length of a string in a cell\.<br />|
|[RowMult](RowMult.md)|Multiply by this number to convert pixels to excel row height units\.<br />|
|[DispMul](DispMul.md)|Number of points in an inch\.<br />|
|[DefaultBrightness](DefaultBrightness.md)|Brightness to keep the image unchanged\.<br />|
|[DefaultContrast](DefaultContrast.md)|Contrast to keep the image unchanged\.<br />|
|[DefaultGamma](DefaultGamma.md)|Gamma to keep the image unchanged\.<br />|
|[DefaultRotation](DefaultRotation.md)|Zero rotation\.<br />|
|[NoTransparentColor](NoTransparentColor.md)|Constant meaning there is no transparent color defined on the image\.<br />|
|[DefaultFormatId](DefaultFormatId.md)|The default XF for a file\. You can also access this value with [TExcelFile.&#8203;Default&#8203;FormatId](../TExcelFile/DefaultFormatId.md)|
|[ObjectPathSeparator](ObjectPathSeparator.md)|String used to separate 2 objects on an object path\.<br />|
|[ObjectPathAbsolute](ObjectPathAbsolute.md)|When an objpath starts with this character, it is an absolute path that includes the object index\.<br />If it doesn't start with it, then the ObjPath doesn't include the original object\.<br />|
|[ObjectPathObjName](ObjectPathObjName.md)|When an objpath starts with this character, it is a path that goes directly to the name of an object\.<br />Note that when more than an object have the same name in the same sheet, this path won't work and you will have to use absolute or relative ones\.<br />|
|[ObjectPathSpId](ObjectPathSpId.md)|When an objpath starts with this character, what follows is a single shape id that identifies the object\.<br />|


## Fields

|Name|Description|
|---|---|
|[ExcelVersion](ExcelVersion.md)|Defines the Excel mode used in this thread\.<br />Note that while on v2007 \(the default\) you still can make xls 97 spreadsheets, so the only reason to change this setting is if you have any compatibility issues \(for example your code depends on a sheet having 65536 rows\)\.<br />IMPORTANT: Do NOT change this value after reading a workbook\. Also, remember that the value is changed for all the reports in all threads\.<br />|
|[KeepMaxRowsAnd&#8203;Columns&#8203;When&#8203;Updating](KeepMaxRowsAndColumnsWhenUpdating.md)|Defines what FlexCel will do when it finds a reference to the last row or column in an Excel 97\-2003 spreadsheet, and it is upgrading to Excel 2007\.<br />If false \(the default\) row 65536 will be updated to row 1048576, and column 256 to column 16384\.<br />If true, references will stay the same\. **Note:** This is a global property, so it affects all threads running\.<br />|
|[MaxNestedCamera&#8203;Objects](MaxNestedCameraObjects.md)|When a camera object references an cell range that includes the camera object, there would be infinite recursion\.<br />This variable determines what is the maximum times that FlexCel will recurse when rendering the camera objects\.<br />|


## Methods

|Name|Description|
|---|---|
|[XlsxCompression&#8203;Level&#8203;ZLib](XlsxCompressionLevelZLib.md)|The compression level in zlib values\.<br />|
|[PdfPngCompression&#8203;Level&#8203;ZLib](PdfPngCompressionLevelZLib.md)|The compression level in zlib values\.<br />|


## Properties

|Name|Description|
|---|---|
|[Max\_Columns](Max_Columns.md)|Maximum column in the spreadsheet\. \(0 based\)\.<br />Note that this number is 1 less than the maximum column count, because this value is 0\-based\. You can use [MaxColCount](MaxColCount.md) to get the number of columns instead\.<br /><br />This number might be 255 if [TExcelFile.&#8203;Excel&#8203;Version](../TExcelFile/ExcelVersion.md) is TExcelVersion\.&#8203;v97\_&#8203;2003 or 16383 otherwise\.<br />|
|[MaxRowCount](MaxRowCount.md)|Returns the maximum number of rows that you can have in a spreadsheet\. This is the same as [Max_Rows](Max_Rows.md) \+ 1\.<br /><br />This number might be 65536 if [TExcelFile.&#8203;Excel&#8203;Version](../TExcelFile/ExcelVersion.md) is TExcelVersion\.&#8203;v97\_&#8203;2003 or 1048576 otherwise\.<br />|
|[MaxColCount](MaxColCount.md)|Returns the maximum number of columns that you can have in a spreadsheet\. This is the same as [Max_Columns](Max_Columns.md) \+ 1\.<br /><br />This number might be 256 if [TExcelFile.&#8203;Excel&#8203;Version](../TExcelFile/ExcelVersion.md) is TExcelVersion\.&#8203;v97\_&#8203;2003 or 16384 otherwise\.<br />|
|[Max\_Rows](Max_Rows.md)|Maximum row in the spreadsheet\. \(0 based\)\.<br />Note that this number is 1 less than the maximum row count, because this value is 0\-based\. You can use [MaxRowCount](MaxRowCount.md) to get the number of columns instead\.<br /><br />This number might be 65535 if [TExcelFile.&#8203;Excel&#8203;Version](../TExcelFile/ExcelVersion.md) is TExcelVersion\.&#8203;v97\_&#8203;2003 or 1048575 otherwise\.<br />|
|[Max\_&#8203;Letters&#8203;InColumn&#8203;Name](Max_LettersInColumnName.md)|Number of letters in a column name\. This is 2 in xls97 \(columns go up to IV\) and 3 in xls2007 \(columns go up to XFD\)|
|[Max\_FormulaLen](Max_FormulaLen.md)|Maximum number of characters in a Formula|
|[Max\_&#8203;Formula&#8203;String&#8203;Constant](Max_FormulaStringConstant.md)|Maximum length of a direct string inside a formula, as in ' = "my long string\.\.\."|
|[Max\_&#8203;Formula&#8203;String&#8203;Constant&#8203;InArray](Max_FormulaStringConstantInArray.md)|Maximum length of a direct string inside a formula, as in ' = "my long string\.\.\."|
|[Max\_&#8203;Formula&#8203;Len97\_&#8203;2003](Max_FormulaLen97_2003.md)|Maximum number of characters in a Formula for an Excel 97 to 2003 spreadsheet\.<br />|
|[Max\_FormulaLen2007](Max_FormulaLen2007.md)|Maximum number of characters in a Formula for an Excel 2007 or newer spreadsheet\.<br />|
|[Max\_DvErrorTitleLen](Max_DvErrorTitleLen.md)|Maximum number of characters in an Error title for a Data Validation\.<br />|
|[Max\_DvErrorTextLen](Max_DvErrorTextLen.md)|Maximum number of characters in an Error text for a Data Validation\.<br />|
|[Max\_DvInputTitleLen](Max_DvInputTitleLen.md)|Maximum number of characters in an Input title for a Data Validation\.<br />|
|[Max\_DvInputTextLen](Max_DvInputTextLen.md)|Maximum number of characters in an Input text for a Data Validation\.<br />|
|[Max\_CommentAuthor](Max_CommentAuthor.md)|Maximum number of characters allowed in the author of a comment\.<br />|
|[Max\_ChartSeries](Max_ChartSeries.md)|Maximum number of series in a chart\.<br />|
|[MaxRowHeight](MaxRowHeight.md)|The maximum height you can set in a row, multiplied by 20\.<br />This is \(409 \* 20 \+ 10\) and means a maximum row height of 409\.5\. Excel says the maximum is 409, but you can enter up to 409\.5|
|[Min\_FontSize](Min_FontSize.md)|Minimum font size allowed in a file\.<br />|
|[Max\_FontSize](Max_FontSize.md)|Maximum font size allowed in a file\.<br />|



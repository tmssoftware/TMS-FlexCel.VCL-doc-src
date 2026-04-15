---
uid: whatsnew
---

# What's new in FlexCel Studio for VCL and FireMonkey

## New in v 7.26 - March 2026


- **Support for the Windows on ARM EC platform.** This release introduces support for Windows on ARM (EC) that was introduced in Delphi 13.1

- **Support for longer strings in formulas.** Before 2026, a hardcoded string in a formula like =len("ABC") was limited to 255 characters. Now the new limit it 4095, and FlexCel was updated to support the new strings. Note that if you save a formula with the new longer strings, it will show as #NAME in older Excel versions

- **Support for longer data validation lists.** In 2026, Excel added the ability to create data validation lists bigger than 255 characters. Now FlexCel can handle those too. Note: To use this feature, you need a very recent Excel, as older ones won't show those validations.

- **Support for new Error codes introduced by Excel.** Now FlexCel can understand the new  #CONNECT, #BLOCKED!, #PYTHON! and #TIMEOUT! errors.

- **Ability to abort a LoopOverUsedRange before the range has been fully visited.** [LoopOverUsedRange](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/LoopOverUsedRange.html) method now has an "abort" parameter which allows to end the loop before the range has been completed.

- **Bug fix.** Images added with the API weren't showing in the macOS26 or iOS26 previewers

- **Bug fix.** Fonts with spaces weren't quoted when creating SVG files, and some browsers wouldn't display the fonts

- **Bug fix.** Small glitches in rendering file could happen when zoom was very small (less than 10%)

- **Bug fix.** Some invalid xlsx files could throw an overflow exception

- **We support now the \n character as intersection operator.** Even when according to the xlsx spec, only space is the intersection operator, Excel also allows \n, so we now allow it too.

- **Bug fix.** When saving single cell tables, the files generated could be invalid

- **Bug fix.** When converting a xlsx file to xls, if the selected row or column was bigger than the maximum allowed in xls, FlexCel would throw an exception. Now it ignores it, and selects the larger cell address that can be saved in xls. This way you can still save the file as xls.



## New in v 7.25 - September 2025


- **Rad Studio 13 support.** Added Rad Studio 13 support

- **New property TExcelFile.OptionsHideObjects lets you set the option to hide objects in a workbook.** The new property [OptionsHideObjects](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/OptionsHideObjects.html) allows you to read or write that property of the workbook. The FlexCel renderer will also honor this setting when you export to PDF, HTML, etc.

- **New overload for creating Hyperlinks.** There is a new overload for creating hyperlinks that automatically separates the url from the text mark. (text mark is the part after # in the url)

- **In FireMonkey, FlexCelPreview could show the images at 2x the size.** In some cases when using FireMonkey, the resolution in FlexCelPreview could go wrong and show the images at twice the size.

- **Improved merged cell handling when exporting or printing.** When calculating the Area to print, Excel in some cases might ignore huge merged cells that end up in the last column or row. In this release, we changed our behavior (never ignoring merged cells) to be similar to Excel (ignore merged cells in particular cases)

- **In master-detail reports with TList&lt;> and and empty master, there could be an exception.** Sometimes when running a report with Lists and master-detail, there could be an exception is the master had 0 records.

- **Bug Fix.** When signing PDFs using CryptoAPI, FlexCel was creating persistent keys on the disk, which could end up filling it.



## New in v 7.24 - April 2025


- **Support for Delphi 12.3 and installing in the 64 bit IDE.** Now FlexCel installs in both the 64bit and 32bit IDEs in Rad Studio 12.3

- **Support Grouping objects.** A new command [GroupObjects](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GroupObjects.html) allows you to group existing shapes.

- **Exporting Conditional Format Icons and DataBars to HTML.** Now we export icons and databars in conditional formats to HTML. All other conditional formats were already exported, so this completes the HTML exporting of conditional formats. All other formats, like SVG or PDF, already exported everything.

- **Exporting gradient cell backgrounds to HTML.** Now gradient background in cells are exported to HTML

- **Faster rendering of files when there are thousands of hidden rows.** Now FlexCel can be up to an order of magnitude faster when converting to pdf or printing files with tens of thousands of hidden rows. Normal files shouldn't be affected much, but they could be a little faster too.

- **Improved rendering of conditional formats icons.** We redrew all icons in conditional formats to look like they do in the latest Excel version.

- **Improved recovery mode.** Recovery mode can now handle more types of invalid files.

- **Bug Fix.** In special cases, charts copied with InsertAndCopy commands wouldn't show in Excel online.

- **Bug Fix.** If a group (but not the shapes inside it) was marked as "do not print" FlexCel would print it anyway. Now we behave as Excel, and only print/don't print depending in the main shape of the group. You can't disable individually printing shapes inside a group.

- **Bug Fix.** When recalculating a formula with =AVERAGEIF that had a a bad argument (for example a string where there should be a reference) FlexCel would throw a Invalid Cast exception. Now it returns #N/A! for the value of the formula.

- **Bug Fix.** A bidirectional report having a full column range could raise a "too many rows" exception in some cases where there were enough rows left.

- **Bug Fix.** When inserting or deleting cell, pivot tables might not move.

- **Bug Fix.** Right-align indented text wasn't correctly exported to HTML.

- **Bug Fix.** When exporting cells with "WrapText=false" to HTML, FlexCel would wrap the enters inside anyway.

- **Bug Fix.** Depending on the font, when exporting a cell to PDF which had an enter but no wrap text, FlexCel could draw an empty rectangle instead of completely ignoring the enter.

- **Bug Fix.** FlexCel could fail to export some files with invalid characters to HTML, due to issues in GDI+.

- **Bug Fix.** FlexCel could fail to open old xlsx files which had notes with non-breaking spaces.

- **Bug Fix.** FlexCel failed to open xls files with a missing OPT record.

- **Gridlines colors are now exported to HTML.** You can change the default color for gridlines in Excel going to Options->Advanced. Now FlexCel will export the correct gridline color to HTML if you change it form silver (It already exported them to PDF and the other formats)



## New in v 7.23 - December 2024


- **Improved accessibility of generated PDF files.** Now the PDFs generated by FlexCel will have a defined Tab order, and pass that accessibility check.

- **Bug Fix.** Improved handling of references in UDFs and Lambda functions. While internally FlexCel manages Lambda functions as user defined functions, they behave differently when handling references. For example, =ISREF(Func(A1)) will return true if this is a lambda function that returns A1, and false if it is a UDF

- **Bug Fix.** When calculating linked files and formulas referred names in other files, there was no way to retrieve the information in UDFs. Also =LET function wouldn't work correctly with those external links.

- **Bug Fix.** Improved the quality of the generated PDF files. When attaching files one record was set as a direct reference when the docs the specs it should be indirect. The files worked anyway, but now they are more strictly correct.

- **Bug Fix.** Improved compatibility with files created by third party tools.



## New in v 7.22 - August 2024


- **Suspended Lazarus support.** Keeping on supporting Trunk FPC/Lazarus build has proven too complex, so we are suspending  the experimental Lazarus/FPC support until there is a stable FPC that we can use. See the [Lazarus guide](https://doc.tmssoftware.com/flexcel/vcl/guides/lazarus-guide.html)

- **Vastly improved memory usage in TFlexCelPreviewer when previewing thousands of sheets at the same time.** The component [FlexCelPreviewer](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Preview/TFlexCelPreviewer/index.html) used to have a cache per sheet, which could grow to the gigabytes when previewing all sheets at the same time. Now the cache is global, reducing the memory used considerably.  For a test file of 3000 sheets, memory went down from 3Gb to 215Mb.

- **FlexCel will now choose the best font to export to PDF if a font is repeated multiple times in the Fonts folder.** When a Font is present twice in the Fonts folder, FlexCel now will choose the best one instead of the last that it read. By best one we mean that if one font is licensed to embed and the other isn't, we prefer the one licensed. If both fonts have the same license, we prefer the one with higher version number. See [https://support.tmssoftware.com/t/tflexcelpdfexport-error-trying-to-embed-font-calibri-in-the-document/23079/12](https://support.tmssoftware.com/t/tflexcelpdfexport-error-trying-to-embed-font-calibri-in-the-document/23079/12)

- **Bug Fix.** FlexCel is now more strict in detecting fonts whose license doesn't allow embedding when exporting to PDF. You can set FlexCel to ignore licensing restrictions by setting the [UnlicensedFontAction](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/UnlicensedFontAction.html#syntax) property in the FlexCelPdfExport object.

- **Bug Fix.** Labels in a Legend when the label range had multiple rows and columns didn't show the same as Excel. See [https://support.tmssoftware.com/t/pie-chart-legend/23077](https://support.tmssoftware.com/t/pie-chart-legend/23077)

- **Bug Fix.** The =COLUMN function could return wrong values when used in an array formula.

- **Bug Fix.** When a sheet had a print area with an invalid sheet, like #REF!A1:A2, FlexCel would assume the print area was A1:A2 anyway in the current sheet. Now the print area is correctly ignored.

- **Bug Fix.** FlexCel could fail to save a file with multiple views of the same file when you added a new sheet to it.

- **Bug Fix.** Improved compatibility with invalid third party files.



## New in v 7.21 - February 2024


- **Support for exporting Persian to PDF.** FlexCel supported arabic but not persian when exporting to PDF. Now both are supported.

- **Bug Fix.** Reviewed bidi algorithm because some arabic numbers could be written in the wrong order when exporting to PDF

- **Bug Fix.** Data labels in scatter chart were incorrect when the axis was reversed.

- **Bug Fix.** When rendering charts that had labels linked to "Value from Cells" FlexCel could fail to render the labels if they weren't manually specified.

- **Bug Fix.** There was an error when rendering PDF Khmer text in some corner cases.

- **Bug Fix.** Header images wouldn't be copied when calling the InsertAndCopySheets overload that takes an array of integers for the sheets to copy.

- **Bug Fix.** SetCellFromHtml could raise an exception with some surrogated unicode characters.

- **Bug Fix.** Charts with hidden series could raise an exception when drawing trendlines.



## New in v 7.20 - December 2023


- **Support for Delphi 12.** We now provide official support for Delphi 12. While Delphi 12 was already supported, we now optimized the codebase for Delphi12.

- **Improved Lazarus support.** We now require a trunk of December 1, 2023 or newer. This version is tested with FPC: 7ecb19f906 and Lazarus: 25c7f3c141

- **Support for creating your own cultures when rendering Excel files.** Now you can override the dates returned by your app so they look exactly like Excel. For more information read the tip  [localized month names](https://doc.tmssoftware.com/flexcel/vcl/tips/localized-month-names.html)

- **Better support for subnormal numbers.** Excel doesn't support [subnormal floating point numbers](https://en.wikipedia.org/wiki/Subnormal_number) and instead converts them to 0. Now FlexCel does the same, instead of saving those numbers to the files.

- **FlexCel is more forgiving with too long data validation formulas.** FlexCel used to raise an error if a formula in a Data Validation is longer than 255 characters, because that is what the spec says and what Excel allows you to enter in its Data Validation Dialog. But, if you save a longer formula by manually editing the xlsx file, Excel won't complain, and the formula will still work. It won't work well, since you won't be able to edit the formula with the UI (and you might be corrupting Excel memory), but Excel won't complain. In order to let you edit those files, now FlexCel won't complain either when you open a file with a longer formula, and it will preserve the formula when you save the file back. But it still will throw an Exception if you try to manually enter that formula, so you know it is invalid. You can still enter the invalid formula manually by turning [Recovery Mode](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RecoveryMode.html) on.

- **Now FlexCel will use its own Random implementation.** This implementation not only is faster and better than Delphi's built-in, but also avoid FlexCel code calling Randomize, and changing the state of the Random Number generator if you were counting in some seed. See [https://support.tmssoftware.com/t/call-to-randomize-when-opening-an-xlsx-spreadsheet/22016/3](https://support.tmssoftware.com/t/call-to-randomize-when-opening-an-xlsx-spreadsheet/22016/3)

- **New setting FlexCelConfig.LocalizedTEXTFunction allows you to fine tune how FlexCel recalculates the "=TEXT()" function.** The setting [FlexCelConfig.LocalizedTEXTFunction](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TFlexCelConfig/LocalizedTEXTFunction.html) allows to change the way the =TEXT() function behaves in FlexCel. Look at the link above for more information.

- **Improved Label rendering when drawing charts.** Now we allow to show the fields "X Value" and "Y Value" in labels of scatter charts. Sometimes the marker if the label was set to show markers was drawn left-aligned, not centered.

- **Removed canvas.getMatrix calls in Android as they are deprecated.** FlexCel now keeps internal track of its Matrix, to avoid calling canvas.getMatrix which was deprecated in Android 16.

- **Bug Fix.** If the column names of a table had a format like "@_@" or similar, FlexCel would apply them and the column name would be wrong. Now the names are the same as in Excel. Some other improvements in handling of column names.

- **Bug Fix.** The XLOOKUP function would return "not found" when searching for a value bigger than any on the list and the match mode was "Exact match or next larger item", when there were empty entries in the list. This is the logical way to do it, it is how Google Sheets does it, and it is how Excel itself behaves in the other match modes. But for this match mode, Excel returns the first empty item in the list, not "not found". Now FlexCel mimics this behavior.

- **Bug Fix.** The SINGLE function could return wrong results in very special cases.

- **Bug Fix.** When autofitting rows FlexCel ignored empty columns formatted with big fonts.

- **Bug Fix.** When parsing some PNGs FlexCel could raise an arithmetic overflow.

- **Bug Fix.** FlexCel could fail to detect circular references in some corner cases, causing a Stack Overflow.

- **Bug Fix.** When drawing Error Bars in charts, if there was no line color assigned, FlexCel would not draw the lines instead of drawing them in Black.

- **Bug Fix.** Some files could show the error: "Value was either too large or too small for an Int32" when opened.



## New in v 7.19.1 - September 2023


- **Bug Fix.** InsertAndCopyRange failed to copy cells in some corner cases



## New in v 7.19 - September 2023


- **New property FlexCelSVGExport.Encoding allows you to change the encoding when generating SVG files.** Now you can change the Encoding of generated SVG files by using the new property [FlexCelSVGExport.Encoding](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelSVGExport/Encoding.html)

- **Breaking Change: Now FlexCel will default the encoding when to exporting to CSV or SVG to UTF-8 without BOM.** FlexCel used to use UTF-8 with BOM to save CSV or SVG files if you didn't specify an encoding. Now the default encoding is UTF-8 with BOM, which is more common. You can still specify an explicit Encoding as UTF-8 with BOM when saving those files if you want to, but if you are not specifying a default, the generated text files will change.

- **Now FlexCel will write the xml inside xlsx files as UTF-8 without BOM.** FlexCel used to write the xml inside xlsx files as UTF-8 with BOM, which is valid and works fine, but some third party tools could have issues reading those files. Excel writes the xml as UTF-8 without BOM itself, so this is not a breaking change. See [https://support.tmssoftware.com/t/save-utf-8-without-bom/21577](https://support.tmssoftware.com/t/save-utf-8-without-bom/21577)

- **Bug Fix.** In some rare cases when you entered #N/A as a parameter in a formula, the full formula would become #N/A. See [https://support.tmssoftware.com/t/handling-of-n-a-in-formuals-on-loading-excel-file/21425](https://support.tmssoftware.com/t/handling-of-n-a-in-formuals-on-loading-excel-file/21425)

- **Bug Fix.** Page numbers in headers and footers were invalid when exporting to SVG.

- **Bug Fix.** GetStringFromCell could return invalid values when the cell contained a formula. This was a regression in v7.18 from v7.17. See [https://support.tmssoftware.com/t/xls-getstringfromcell-read-cell-in-version-7-17-but-not-in-v7-18/21545](https://support.tmssoftware.com/t/xls-getstringfromcell-read-cell-in-version-7-17-but-not-in-v7-18/21545)

- **Bug Fix.** FlexCel could write some invalid DXF records when saving table styles to xls files.

- **Bug Fix.** InsertAndCopyRange could fail to copy cells in some corner cases



## New in v 7.18 - August 2023


- **Support for the new Excel2023 default format including the default aptos font.** Now when calling [ExcelFile.NewFile](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/NewFile.html) there is a new option to create a file with the new office 2023 theme and fonts.

- **Added new units FlexCel.VCLSupport, FlexCel.FMXSupport, FlexCel.LCLSupport and FlexCel.SKIASupport to replace VCL.FlexCel.Core, FMX.FlexCel.Core, LCL.FlexCel.Core and SKIA.FlexCel.Core respectively.** The units  VCL.FlexCel.Core, FMX.FlexCel.Core, LCL.FlexCel.Core and SKIA.FlexCel.Core still work, but we added new units FlexCel.PlatformSupport which should be preferred now as they behave better in C++ builder. You can read more about this change at [VCL.FlexCel.Core vs FlexCel.VCLSupport](https://doc.tmssoftware.com/flexcel/vcl/tips/vcl-flexcel-core-vs-flexcel-vclsupport.html)

- **New property TExcelFile.PrintComments allows to directly manipulate how to print the comments.** The new property [ExcelFile.PrintComments](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintComments.html) allows you to directly change how comments are printed without having to use  [TExcelFile.PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html).

- **FlexCel can now render comments "As displayed".** When  [ExcelFile.PrintComments](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintComments.html) is "As Displayed", FlexCel will now print and export to PDF/HTML/SVG the comments as they are displayed. See  [https://support.tmssoftware.com/t/excel-with-comments-export-to-pdf-with-comments-showing/19377](https://support.tmssoftware.com/t/excel-with-comments-export-to-pdf-with-comments-showing/19377)

- **New property TExcelFile.PrintErrors allows to directly manipulate how to print the errors in formulas inside the sheet.** The new property [ExcelFile.PrintErrors](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintErrors.html) allows you to change how the errors in the sheet will be printed.

- **FlexCel can now render error in formulas according to the printer settings.** When  [ExcelFile.PrintErrors](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintErrors.html) is not "As Displayed", FlexCel will now print and export to PDF/HTML/SVG the correct values.

- **New properties TExcelFile.PrintOptionsInitializedFromPrinter, TExcelFile.PrintOverThenDown and TExcelFile.PrintDraftQuality.** The new properties  [ExcelFile.PrintOptionsInitializedFromPrinter](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptionsInitializedFromPrinter.html), [ExcelFile.PrintOverThenDown](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOverThenDown.html) and  [ExcelFile.PrintDraftQuality](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintDraftQuality.html)  allow to change the  [TExcelFile.PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html) in a simpler way. Now there are properties to change every one of the individual  [PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html), and so APIMate won't suggest changing  [PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html), but the standalone properties instead. APIMate will still show the code to change  [PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html), but commented out.

- **ApiMate won't show PrinterDriverSettings by default.** PrinterDriverSettings are a huge binary blob which can make the output of APIMate much harder to read. It was already commented out, but now it is not shown at all by default. There is a checkbox to show it if you need it.

- **Bug Fix.** When rendering charts inside xlsx files, sometimes FlexCel could fail to render the correct colors of some series, using black instead.

- **Bug Fix.** Formatted numbers inside cells with "Shrink to fit" didn't shrink when exporting to HTML

- **Bug Fix.** &lt;#if> tag in reports would consider the condition true if it evaluated to NAN or a number.

- **Bug Fix.** &lt;#ref> tag in reports now returns a real reference instead of a string with the cell reference. While for most uses it is the same, in some cases like in the "Cell" function, the old &lt;#ref> tag wouldn't work.



## New in v 7.17 - June 2023


- **Improved API for defining columns in tables.** Now you can define a totals formula or a column formula for the columns in the table, if needed. As usual, APIMate will show you how to do it.

- **Now FlexCel preserves digital signatures in macros.** When you have digitally signed macros in a file, now FlexCel will preserve them when opening and saving that file

- **New property  DeleteEmptyBandsFixed in FlexCelReport controls what to do with empty fixed bands.** The new function [DeleteEmptyBandsFixed ](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/DeleteEmptyBandsFixed.html) lets you define what happens if a fixed band has zero records.

- **Improved the experimental Lazarus support.** FlexCel can't still be compiled with Lazarus stable as it hasn't got anonymous methods yet. But we've modified the code to adapt for the changes in Lazarus trunk.

- **Bug Fix.** When recreating a table by calling AddTable and SetTable, the cell references could become invalid

- **Bug Fix.** The functions IFERROR, ISERROR and ISERR could sometimes return the error instead of the result of the function.

- **Bug Fix.** The functions COUNTIF, SUMIF and similar could behave wrong in some cases where you used wildcards. See [https://support.tmssoftware.com/t/countif-formula-with-wildcard-failing-after-recalc-method-is-called/19266](https://support.tmssoftware.com/t/countif-formula-with-wildcard-failing-after-recalc-method-is-called/19266)

- **Bug Fix.** The function [TRIM](https://support.microsoft.com/en-us/office/trim-function-410388fa-c5df-49c6-b16c-9e5630b479f9) in Excel removes double spaces in the middle of a text, while FlexCel's implementation would remove only spaces at the beginning at end. Also Excel's TRIM only removes spaces (character 32) and not other whitespace like tabs. FlexCel's implementation now does the same.

- **Bug Fix.** FlexCel could fail to read some encrypted files raising an error 'Error in CryptoAPI: $80090004'.

- **Bug Fix.** The function =NUMBERVALUE() could throw an Exception in some border cases

- **Bug Fix.** Setup would fail to install if there was a "," in the path



## New in v 7.16 - September 2022


- **Support iOSSimulator Arm64.** There is now support for the new iOS Simulator Arm in Delphi 11.2

- **Support for different numeric systems in cell formatting.** Now if you format a cell with a different numeric system like for example "[$-2000000]#,##0.00", FlexCel will render those numbers correctly. (see [https://ansarichat.wordpress.com/2018/02/20/how-to-type-arabic-numerals-in-excel/](https://ansarichat.wordpress.com/2018/02/20/how-to-type-arabic-numerals-in-excel/) )

- **Bug Fix.** When rendering charts that used =Offset to define the data, and some columns or rows were hidden, FlexCel could fail to hide the values when the chart was set to not plot hidden cells.

- **Bug Fix.** In some rare cases when there was merged cells whose first cell was hidden the background might not be exported to pdf.

- **Bug Fix.** If printing gridlines and there were hidden columns or rows, the gridlines could be printed over the real borders of a cell.

- **Bug Fix.** When exporting to CSV, there could be errors if you manually set cell values to NaN.

- **Bug Fix.** If exporting to PDF and the "normal" font of the spreadsheet was Calibri 9 columns could be wider than expected.

- **Bug Fix.** When exporting in Linux the pdfs could be wrong, due to a bug in Delphi. This release workarounds this bug and allows correct exporting from Linux.

- **Bug Fix.** FlexCel could hang while loading some invalid third-party files.



## New in v 7.15 - July 2022


- **Experimental Lazarus support.** We now experimentally support compiling in Lazarus. See the new [Lazarus guide](https://doc.tmssoftware.com/flexcel/vcl/guides/lazarus-guide.html) for more details.

- **Support for functions FILTER, SORT, SORTBY, and UNIQUE.** There is now support for the [functions introduced in office 2021](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-functions.html#added-functions-in-office-2021) : [FILTER](https://support.microsoft.com/en-us/office/filter-function-f4f7cb66-82eb-4767-8f7c-4877ad80c759), [SORT](https://support.microsoft.com/en-us/office/sort-function-22f63bd0-ccc8-492f-953d-c20e8e44b86c), [SORTBY](https://support.microsoft.com/en-us/office/sortby-function-cd2d7a62-1b93-435c-b561-d6a35134f28f), and [UNIQUE](https://support.microsoft.com/en-us/office/unique-function-c5ab87fd-30a3-4ce9-9d1a-40204fb85e1e).

- **Support for functions MAP, REDUCE, SCAN, MAKEARRAY, BYROW, and BYCOL.** There is now support for the [functions introduced in office 365](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-functions.html#added-functions-in-office-365) : [MAP](https://support.microsoft.com/en-us/office/map-function-48006093-f97c-47c1-bfcc-749263bb1f01), [REDUCE](https://support.microsoft.com/en-us/office/reduce-function-42e39910-b345-45f3-84b8-0642b568b7cb), [SCAN](https://support.microsoft.com/en-us/office/scan-function-d58dfd11-9969-4439-b2dc-e7062724de29), [MAKEARRAY](https://support.microsoft.com/en-us/office/makearray-function-b80da5ad-b338-4149-a523-5b221da09097), [BYROW](https://support.microsoft.com/en-us/office/byrow-function-2e04c677-78c8-4e6b-8c10-a4602f2602bb), and [BYCOL](https://support.microsoft.com/en-us/office/bycol-function-58463999-7de5-49ce-8f38-b7f7a2192bfb).

- **Support for functions TEXTBEFORE, TEXTAFTER, TEXTSPLIT, HSTACK, VSTACK, TOROW, TOCOL, WRAPROWS, WRAPCOLS, TAKE, DROP, CHOOSEROWS, CHOOSECOLS, and EXPAND.** There is now support for the new [functions introduced in office 365 beta](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-functions.html#added-functions-in-office-365) : [TEXTBEFORE](https://support.microsoft.com/en-us/office/textbefore-function-d099c28a-dba8-448e-ac6c-f086d0fa1b29), [TEXTAFTER](https://support.microsoft.com/en-us/office/textafter-function-c8db2546-5b51-416a-9690-c7e6722e90b4), [TEXTSPLIT](https://support.microsoft.com/en-us/office/textsplit-function-b1ca414e-4c21-4ca0-b1b7-bdecace8a6e7), [HSTACK](https://support.microsoft.com/en-us/office/hstack-function-98c4ab76-10fe-4b4f-8d5f-af1c125fe8c2), [VSTACK](https://support.microsoft.com/en-us/office/vstack-function-a4b86897-be0f-48fc-adca-fcc10d795a9c), [TOROW](https://support.microsoft.com/en-us/office/torow-function-b90d0964-a7d9-44b7-816b-ffa5c2fe2289), [TOCOL](https://support.microsoft.com/en-us/office/tocol-function-22839d9b-0b55-4fc1-b4e6-2761f8f122ed), [WRAPROWS](https://support.microsoft.com/en-us/office/wraprows-function-796825f3-975a-4cee-9c84-1bbddf60ade0), [WRAPCOLS](https://support.microsoft.com/en-us/office/wrapcols-function-d038b05a-57b7-4ee0-be94-ded0792511e2), [TAKE](https://support.microsoft.com/en-us/office/take-function-25382ff1-5da1-4f78-ab43-f33bd2e4e003), [DROP](https://support.microsoft.com/en-us/office/drop-function-1cb4e151-9e17-4838-abe5-9ba48d8c6a34), [CHOOSEROWS](https://support.microsoft.com/en-us/office/chooserows-function-51ace882-9bab-4a44-9625-7274ef7507a3), [CHOOSECOLS](https://support.microsoft.com/en-us/office/choosecols-function-bf117976-2722-4466-9b9a-1c01ed9aebff), and [EXPAND](https://support.microsoft.com/en-us/office/expand-function-7433fba5-4ad1-41da-a904-d5d95808bc38).

- **New SHEET VISIBLE tag that allows to change the visibility of a sheet in a report.** You can now use the new [Sheet Visible](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-tag-reference.html#sheet-visible) tag to hide or unhide sheets. See [https://support.tmssoftware.com/t/hide-worksheet-in-report-tags/18336/2](https://support.tmssoftware.com/t/hide-worksheet-in-report-tags/18336/2)

- **You can now run reports on TList&lt;primitive> like  TList&lt;double>.** Now you can use a list of a primitive type like TList&lt;string> in reports. You have to write &lt;#list.Value> in the template for it to work. See the modified example of [using lists as datasets](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/reports/reports-from-lists/index.html). See [https://support.tmssoftware.com/t/using-list-as-datasource/18513/4](https://support.tmssoftware.com/t/using-list-as-datasource/18513/4)

- **Ability to change the newline separator when exporting to CSV or Fixed-lenght text files.** By default FlexCel exports to CSV or fixed length using the newline separator from the OS. (that's CR/LF in Windows and LF in Unix/macOS). Now you can explicitly define the newline string when calling [Export](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/Export.html) See [https://support.tmssoftware.com/t/settings-for-new-line-character-when-saving-texcelfile-to-csv/17886/3](https://support.tmssoftware.com/t/settings-for-new-line-character-when-saving-texcelfile-to-csv/17886/3)

- **Support for Array formulas, UDFs, external names and Lambda names in Tokens.** [Tokens](https://doc.tmssoftware.com/flexcel/vcl/tips/using-tokens-to-get-information-from-formulas.html) now support Array formulas, user-defined functions (UDF), names that refer to external files, and Lambda names (like if you write in a formula "=MyName(4)" and MyName is a lambda function.). Standalone lambda functions (without using names) were already supported. The only thing not supported in tokens right now is what-if tables.

- **Function "INDEX" is now array-enabled.** Now you can pass arrays in the col and row parameters of the [INDEX](https://support.microsoft.com/en-us/office/index-function-a5dcf0dd-996d-40a4-a822-b56b061328bd) function and FlexCel will return an array of results.

- **Improved behavior when inside Docker containers.** Now when you try to run FlexCel in a Docker container without any fonts installed, FlexCel will tell you the problem and how to fix it. There is also a [new tip](https://doc.tmssoftware.com/flexcel/vcl/tips/running-flexcel-inside-docker-containers.html) explaining how to handle fonts inside docker containers.

- **Bug Fix.** The functions SWITCH and IFS could fail is some border cases.

- **Bug Fix.** Bubble charts could render bubbles of the wrong size if there were empty points in the chart data with bubble size different from 0.

- **Bug Fix.** Negative dates now show empty instead of "########" when they are labels of charts. This is the behavior Excel has too.

- **Bug Fix.** Cells with diagonal borders, but borders style set to none could be rendered by FlexCel in some cases.

- **Bug Fix.** Some files containing khmer characters (or other complex scripts) could raise an exception when exporting to pdf.

- **Bug Fix.** Sometimes RenderObjects would not render the images. See [https://support.tmssoftware.com/t/images-disappear-sometimes/18567/6](https://support.tmssoftware.com/t/images-disappear-sometimes/18567/6)

- **Bug Fix.** There could be errors in some specific cases when copying sheets from one file to another which had linked formulas.

- **Bug Fix.** The limit for custom formats in xls files was in 4000 when it really is 4050. We've updated FlexCel to allow 4050 custom formats when saving as xls.

- **Bug Fix.** The [TYPE](https://support.microsoft.com/en-us/office/type-function-45b4e688-4bc3-48b3-a105-ffa892995899) function didn't return 128 for lambda functions.

- **Bug Fix.** When third-party files had invalid modify/creation dates, FlexCel would refuse to open them. Now it will just ignore invalid dates and let those properties empty.

- **Bug Fix.** APIMate generated some code with invalid syntax in C++.



## New in v 7.14 - January 2022


- **Support for bubble charts.** Now [FlexCel can render Bubble charts](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-charts.html#bubble). You can also enter them with the API and APIMate will show you the code to do it.

- **New &lt;#Swap Series> tag for reports.** The new [&lt;#Swap Series>](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-tag-reference.html#swap-series) tag allows you to create charts that grow or decrease their number of series according to the data available.

- **New CustomizeChart event for reports.** The new [CustomizeChart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/CustomizeChart.html) event allows you to further customize the charts in the report once they have been generated.

- **Support for optional lambda parameters.** There is now full support for the new [optional lambda parameters in Excel](https://insider.office.com/blog/new-lambda-functions-available-in-excel).

- **IsOmitted function support.** There is now full support for the new [IsOmitted function](https://support.microsoft.com/en-us/office/isomitted-function-831d6fbc-0f07-40c4-9c5b-9c73fd1d60c1).

- **Improved recovery mode.** [RecoveryMode](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RecoveryMode.html) can now load more types of invalid files.

- **Support for localized versions of the CELL function.** Now you can write the first argument of function CELL in 24 languages, and FlexCel will understand them anyway. Before only English was understood. The languages added are Catalan, Croatian, Czech, Danish, Dutch, Finnish, French, Galician, German, Hungarian, Italian, Kazakh, Korean, Norwegian, Polish, Portuguese-Brazil, Portuguese-Portugal, Russian, Slovak, Slovenian, Spanish, Swedish, Turkish and Ukrainian

- **Bug Fix.** Now FlexCel will throw an exception if you try to save a chart with more than 255 series. Before this release, FlexCel would just save the file, but a file with more than 255 series crashes Excel.

- **Bug Fix.** APIMate wouldn't report deleted chart titles, which could lead to chart titles appearing when there was a series with a name.

- **Bug Fix.** It was impossible to manually enter lambda formulas referring to names if [AllowEnteringUnknownFunctionsAndNames](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/AllowEnteringUnknownFunctionsAndNames.html) was false.

- **Bug Fix.** A horizontal fixed band in a report would insert columns if using more than the fixed space, instead of just overwriting the cells.

- **Bug Fix.** Sometimes it was not possible to read properties from xls files.



## New in v 7.13 - December 2021


- **Support for office 2021.** While we already supported it since we support Office 365, we added enumerations to create files with office 2021 defaults, and identify the file as being created by Excel 2021.

- **Support for Radar charts.** Now FlexCel can render Radar (Spider) charts. You can also enter them with the API and APIMate will show you the code to do it.

- **Support for the "Black and white" printing option in Excel.** Now when exporting to pdf, html, or printing, FlexCel will honor the "Black and White" option in the print options. Note that Black and White priniting in Excel doesn't mean to print in grayscale, but printing all backgrounds white and all lines black no matter the actual colors. It also depends in what you render, for example colors in a chart bar will be replaced by patterns. There is also a new convenience method [PrintBlackAndWhite](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintBlackAndWhite.html) that will let you modify the [PrintOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/PrintOptions.html) directly to print in black and white.

- **Ability to set the bottom row when specifying an autofilter.** Now [SetAutoFilter](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetAutoFilter.html) can have an extra parameter to specify the bottom row of the Autofilter. Note that if there are more rows after the bottom row, those will be included anyway. Setting the bottom row is only useful to ensure that rows *up to* bottom rows are included, no matter if there are blank cells in the middle.

- **New convenience method LoopOverUsedRange that can be used to loop over a range of cells.** There is a new method [LoopOverUsedRange](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/LoopOverUsedRange.html) which will let you loop over a range of cells in a simple and efficient way.

- **New properties TextHorizontalOverflow and TextVerticalOverflow in TShapeProperties.** The new properties  [TextHorizontalOverflow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextHorizontalOverflow.html) and [TextVerticalOverflow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextVerticalOverflow.html)  allow you to set how the text overflows a shape. This corresponds to the checkbox in Excel "Allow text to overflow shape"

- **New convenience properties TextRotated, TextVerticalAlignment, TextHorizontalAlignment and LockText in TShapeProperties.** The new properties  [LockText](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/LockText.html), [TextVerticalAlignment](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextVerticalAlignment.html) and [TextHorizontalAlignment ](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextHorizontalAlignment.html) allow to set or get [TextFlags](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextFlags.html) in a simpler way.
The new property [TextRotated](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextRotated.html) allows to set [TextRotation](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/TextRotation.html) in a simpler way. APIMate now shows those properties instead of TextFlags and TextRotation. Read more in the tip about [xlsx and xls approaches to text rotation](https://doc.tmssoftware.com/flexcel/vcl/tips/text-rotation-in-xls-and-xlsx.html).

- **New method  SetObjectProperties to set all the object properties in one step.** There is a new method [SetObjectProperties](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetObjectProperties.html) that will allow to easily change the properties of an object. You just call [GetObjectProperties](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetObjectProperties.html), modify the values you want and then call [SetObjectProperties](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetObjectProperties.html).

- **New property IsLocked in TShapeOptions.** There is a new property  [IsLocked](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/IsLocked.html) which controls how if the shape is locked or not.

- **New overloaded version of SetObjectProperty for booleans.** There is a new overload of [SetObjectProperty](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetObjectProperty.html) that will allow you to set the property directly, without calculating the position in the set.

- **Improved legend drawing in charts.** Legends items in charts should render better now when some items are empty, and multiline items were improved too.

- **Bug Fix.** Background of Axis text set by the API was ignored.

- **Bug Fix.** Rotation of Axis text set by the API was ignored.

- **Bug Fix.** When setting an Axis position in a chart to cross in the max value with the API, the value was ignored and it always used the manual crossing point.

- **Bug Fix.** Some hidden fills in files could be read as normal fills and so would appear if reading and saving a file.

- **Android demos now use AndroidX instead of Support Library.** The [Android Support Library](https://developer.android.com/topic/libraries/support-library) is deprecated and replaced by [AndroidX](https://developer.android.com/jetpack/androidx). So we've modified the demos using the old Support library to use AndroidX instead. Also the [documentation](https://doc.tmssoftware.com/flexcel/vcl/guides/android-guide.html#sharing-files) has been updated to use AndroidX.



## New in v 7.12 - October 2021


- **PowerBI Data models are now preserved.** FlexCel will now preserve the spreadsheet data models used by Power BI technologies (PowerPivot, PowerMap, etc) inside xlsx files.

- **Bug Fix.** GetImageProperties could return an index out of bounds when passed a valid imageindex but there were grouped images.

- **Bug Fix.** [TFlexCelPrintDocument.PrintAllVisibleSheets](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPrintDocument/PrintAllVisibleSheets.html#tflexcelprintdocumentprintallvisiblesheets-method) wouldn't print if resetPageNumberOnEachSheet was true.

- **Bug Fix.** In Delphi XE, XE2 and XE3 there could be issues with sheet names using accented characters. This was already working fine for XE4 or newer.

- **Setup now allows to enable full RTTI.** FlexCel by default disables RTTI on its classes and methods to produce smaller executables. But some apps like tms scripter studio require RTTI to work. Now the installer offers the option to enable RTTI. With RTTI enabled, you can expect a size increase in your exes of 2-3mb.



## New in v 7.11 - September 2021


- **Support for RAD Studio 11.** Official support for Rad Studio 11

- **New overloads of methods for getting image information that take objectIndexes instead of imageIndexes.** The methods [GetImageProperties](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetImageProperties.html), [GetImageName](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetImageName.html), [SetImageProperties](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetImageProperties.html), [DeleteImage](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/DeleteImage.html) and [ClearImage](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ClearImage.html) now have overloads taking an objectIndex/objectPath pair instead of an imageIndex.

- **New methods to convert between imageindexes and objectindexes with support for grouped shapes.** The new methods [ImageIndexToObjectPath](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ImageIndexToObjectPath.html) and [ObjectPathToImageIndex](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ObjectPathToImageIndex.html) can convert between imageIndexes and objectIndexes taking care of nested objects. The existing methods would only work in non-grouped objects.

- **You can now read and write the links of a camera object.** The methods [GetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetShapeLinkedCell.html) and [SetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetShapeLinkedCell.html) now work in picures too, allowing to read or create camera objects besides to shapes with their text linked.

- **Improved loading of Excel 3, 4 and 95 files.** Now FlexCel can load camera objects in Excel 3, 4 and 95 files. It will also load the image names for images in Excel 95 files (Excel 4 and older don't store an image name)



## New in v 7.10 - August 2021


- **Support for SVG images embedded in xlsx files.** Excel has recently started allowing SVG images inside xlsx files. This releases adds full support for adding and reading SVG images to/from xlsx files. Note that we don't currently have a SVG renderer, so to add a SVG image you need to provide both an SVG and a PNG image. you can get more details in [this tip](https://doc.tmssoftware.com/flexcel/vcl/tips/svg-files-inside-xlsx-files.html)

- **Breaking Change: Now when exporting to HTML and SVG, the SVG images stored inside the file will be embedded as SVG.** Before, FlexCel would always embed the PNG fallback image. To keep the old behavior, there are 2 new properties: [ TFlexCelHtmlExport.RasterizeSVGImages](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelHtmlExport/RasterizeSVGImages.html) and [ TFlexCelSvgExport.RasterizeSVGImages](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelSvgExport/RasterizeSVGImages.html)

- **Ability to add chart sheets with the API.** There is a new method [AddChartSheet](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/AddChartSheet.html) which will allow you to add chart sheets with the API. As usual, APIMate will show you the code needed to add a chart sheet.

- **Ability to link shape text to cells via the API.** The new methods [GetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetShapeLinkedCell.html),  [SetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetShapeLinkedCell.html) in [ TExcelFile](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/) and [GetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IExcelChart/GetShapeLinkedCell.html),  [SetShapeLinkedCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IExcelChart/SetShapeLinkedCell.html) in [ IExcelChart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IExcelChart/) allow you to read and write linked text in shapes.

- **Full Window management via API.** There is a new property [ActiveWindow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ActiveWindow.html) which allows you to select the [window](https://support.microsoft.com/en-ie/office/close-workbooks-or-workbook-windows-ca74dca4-8d2f-43f9-84e1-f9a1b1621d26) you are working on. You can then set the zoom, selected cells, etc. for that window, leaving the other windows unaffected. The new commands  [AddWindow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/AddWindow.html) and  [DeleteWindow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/DeleteWindow.html) allow you to add or delete windows.  [WindowCount](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/WindowCount.html) will let you know how many windows you have in the file. [ActiveSheetForActiveWindow](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ActiveSheetForActiveWindow.html) will let you select an active sheet for each window, even if the ActiveSheet for FlexCel won't change.

- **Includes in reports can now be FIXED.** Now you can use the word FIXED in the "Shift type" parameter of the [include tag](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-tag-reference.html#include) . Fixed includes won't insert rows or columns, just overwriting the cells in the main report.

- **Support for recalculation of function NUMBERVALUE.** Now FlexCel can recalculate the [NUMBERVALUE](https://support.microsoft.com/en-us/office/numbervalue-function-1b05c8cf-2bfa-4437-af70-596c7ea7d879) function introduced in Excel2013. As usual, the list of supported Excel functions is at [supported-excel-functions.html](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-functions.html) in the docs

- **Ability to set shape effects like glow or shadow with the API.** Now you can set shape effects with the API, and APIMate will tell you the code to do it.

- **Improved recalculation speed.** We've implemented caches for some common formula patterns which should make your recalculations go much faster if your files use those patterns.

- **Improved support for Tiff and Gif images.** FlexCel used to convert tiff and giff images to png when loading them, so they could be saved inside xls files (xls files don't support those formats). Now FlexCel will preserve the file formats, and only convert them to pngs if you are saving in xls format.

- **Improved HTML5 exporting.** We've made the html5 files generated by FlexCel more compliant with html5 validators.

- **Improved drawing of shape shadows for xlsx files.** FlexCel will now render better the shadows in shapes inside xlsx files.

- **Improved drawing of log-chart gridlines.** Now the gridlines in logarithmic charts behave more similar to Excel in border cases

- **Comments added with the API won't include a shadow.** Now when you add a comment with the API, it won't include a shadow, same as modern Excel doesn't when you add a note. You can always use SetCommentProperties to add a shadow if you want to, and APIMate will show you the code.

- **Bug Fix.** Excel could crash with files including charts with Soft edges effect.

- **Improved handling of linked text in autoshapes.** Now FlexCel will preserve the properties of empty linked text in autoshapes. It will also handle better shapes with text linked to names that reference different sheets.

- **Bug Fix.** Sometimes FlexCel could fail to parse formulas with hard-coded arrays which had strings inside.

- **Bug Fix.** Conditional formats with iconsets where some values of the iconset were "No icon" could be saved wrong.

- **Bug Fix.** Comments could lose or gain a shadow when converting from xls to xlsx or xlsx-strict. Also colors in the comments could be wrong in border cases.

- **Bug Fix.** When renaming tables FlexCel wasn't renaming references in column formulas

- **Bug Fix.** FlexCel could crash when rendering chart labels with "Value from cells" if the range existed but was null.

- **Bug Fix.** Accessing some Conditional formats with inner borders could cause an Exception.

- **Bug Fix.** FlexCel would not export to pdf 3rd-party files which had unreadable file properties.

- **Bug Fix.** When using &lt;#database.#rowcount> in expressions outside the sheet, you could get an exception.

- **Bug Fix.** FlexCel could throw an exception when inserting columns in xls files with invalid external references

- **Bug Fix.** FlexCel could throw an Exception when manually adding an autoshape to a chart that was created via the API.

- **Bug Fix.** Better compatibility with files generated by FastReports. Excel ignores border style 0 and fill styles 0 and 1, and now FlexCel ignores those too.

- **Better handling of third-party xls files.** Now FlexCel will convert the deprecated labels in biff8 xls files to sstlabels instead of keeping them as-is, allowing for much decreased memory usage when reading those files, and smaller result files.

- **Bug Fix.** Text to autoshapes added with the API would always be left-aligned.

- **Bug Fix.** FlexCel could report the BOM when reading custom XML parts inside xlsx files. Now the BOM is stripped out as it should.

- **Bug Fix.** Reports using TDataSets in master-detail could get the wrong results if both master and detail had the same underlying dataset.

- **Bug Fix.** ApiMate would not suggest how to add a shape without borders



## New in v 7.9 - April 2021


- **Support for functions LAMBDA and LET.** We've reworked the recalculation engine to add support for [LAMBDA](https://www.microsoft.com/en-us/research/blog/lambda-the-ultimatae-excel-worksheet-function/) and [LET](https://support.microsoft.com/en-us/office/let-function-34842dd8-b92b-4d3f-b325-b8b8f9908999) functions. With Lambda, the calculation engine is now turing-complete.

- **Support for functions SINGLE, VALUETOTEXT and VALUETOARRAY.** Added support for [SINGLE](https://support.microsoft.com/en-us/office/implicit-intersection-operator-ce3be07b-0101-4450-a24e-c1c999be2b34), [VALUETOTEXT](https://support.microsoft.com/en-us/office/valuetotext-function-5fff61a2-301a-4ab2-9ffa-0a5242a08fea) and [ARRAYTOTEXT](https://support.microsoft.com/en-us/office/arraytotext-function-9cdcad46-2fa5-4c6b-ac92-14e7bc862b8b) functions.

- **Support for rendering multi-level labels in category axis.** In Excel you can set a category axis to have more than one row/column, and Excel will render those multi-level ranges in a different way than normal ranges. Now FlexCel will behave the same.

- **Support for legend keys in chart labels.** Now when exporting to PDF/HTML, if the option "Legend key" is enabled in the label options of a chart, FlexCel will render them.

- **Support for "Label contains Value from range" option in charts.** Now FlexCel will correctly handle the "Label Contains: " "Value from Cells" options for chart labels available in newer Excel versions. They will be exported to PDF/HTML and APIMate will show the code to create them in your programs.

- **Breaking Change: The property LabelValues in IDataLabel changed from TArray&lt;TCellValue> to TArray&lt;TDrawingValue>.** In order to support the "Label contains Value range" options in charts, we needed to change the type of the array to a more complete type. The current type was used in xls files, but xlsx files have a more complex type.
While this is a breaking change, it should break at compile time. If you get an error compiling a line like `Title.LabelValues := TCellValueArray.Create('This is my Chart!');` change it to `Title.LabelValues := TDrawingValueArray.Create(TDrawingValue.Create('This is my Chart!'));`  ApiMate will now show the updated method.

- **Improved drawing of x-axis in charts.** Now FlexCel will automatically adjust the x-axis labels to 45 degrees if needed, and also take the space from near labels if those are empty.

- **TXls3DRange now supports an external filename.** The object [TXls3DRange](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TXls3DRange/index.html) now has a property with the filename, in case that the range is from another file. This allows to use external files in user-defined functions.

- **Hyperlink Base support.** Now FlexCel will correctly preserve [Hyperlink Base](https://support.microsoft.com/en-us/office/work-with-links-in-excel-7fc80d8d-68f9-482f-ab01-584c44d72b3e) in xlsx files (it was already preserved in xls). Now the hyperlink base is also used when exporting to HTML, SVG or PDF.

- **Support for using an expression like &lt;#joinedtable.tablejoined.\*> to make a generic report in only one of the joined tables.** Now when you join tables in the template you can use &lt;#joinedtable.tablejoined.\*> or &lt;#joinedtable.tablejoined.\**> to create a generic report only in the fields of that subtable.

- **The &lt;#ref> tag can now use tags in its parameters.** Now you can write something like &lt;#ref(&lt;#dataset.#rowcount>,3)>. Before this version tags were not allowed as parameters.

- **New property "IsCameraObject" in TImageProperties.** The new property [IsCameraObject](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IImageProperties/IsCameraObject.html) lets you know if an image is a camera object or not.

- **Improved compatibility with xlsx files created by SoftMarker Office.** SoftMaker office adds many extensibility points in places of the xlsx where they are not allowed. FlexCel complained about that, but in the new version we ignore the ones we could identify.

- **The SKIA lib used in Linux now runs in Ubuntu 16.04 and newer.** We have updated the SKIA library we use for graphics support in Linux to the latest, and compiled it in Ubuntu 16.04 so it is compatible with 16.04 and newer.

- **Axis labels will now render with a background color if they have one.** Now the axis labels will render the background color if you assign a color to them.

- **Bug Fix.** FlexCel would always render labels in the category axis as not "linked to source" even if they were.

- **Bug Fix.** Labels which come from cells that are formatted to show negative values in different colors show with that color in Excel, except in pie charts. FlexCel used to ignore that color, not it will display it.

- **Bug Fix.** When rendering xlsx charts, labels which were manually positioned would ignore the default  numeric formatting.

- **Bug Fix.** Structured references with text formatting could be saved wrong to new xlsx files.

- **Bug Fix.** Rotated labels in charts could a little below or above from where they should go.

- **Bug Fix.** FlexCel could fail to parse a formula where the sheet name started with some Unicode characters, like for example "※MySheet"

- **Bug Fix.** When reading structured references in Virtual Mode, there could be an access violation.

- **Bug Fix.** FlexCel didn't preserve or render text linked to cells in shapes inside charts.

- **Bug Fix.** FlexCel would allow you to name a sheet starting with a single quote ('), and that would cause an invalid file. Now the quote at the start of the name will be replaced by a "_" as other invalid characters do.

- **Bug Fix.** There could be a memory leak when calling TFlexCelReport.ClearTables



## New in v 7.8 - November 2020


- **Support for reading fonts from the disk even if the graphics library returns that information.** There is a new property in FlexCelConfig: [ForcePdfFontsFromDisk](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/FlexCelConfig/ForcePdfFontsFromDisk) which allows you to select if FlexCel should use the font data returned by the graphics library if possible, or always scan a folder with fonts.

- **Improved compatibility with invalid xls files.** Now FlexCel can ignore invalid ministreams when reading corrupt/invalid xls files.



## New in v 7.7 - October 2020


- **Improved handling of unknown parts inside xlsx files and improved Google sheets compatibility.** Now FlexCel has a more solid implementation for preserving unknown parts and  relationships inside xlsx files. This fixes issues that could happen when editing xlsx files generated by google sheets.

- **Bug Fix.** When copying a sheet to a different file, ImageCount in the target file would return 0 even if there were images.

- **Bug Fix.** FlexCel wouldn't allow some unicode characters in 3d formulas, while Excel would allow them.

- **Bug Fix.** Improved support for camera objects. A new property [MaxNestedCameraObjects](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TFlxConsts/MaxNestedCameraObjects.html) allows to specify how many times a camera object can recursively draw itself.

- **Bug Fix.** FlexCel could not read some files with deleted what-if tables.



## New in v 7.6.4 - July 2020


- **New syntax for ALIAS DataSets.** The ALIAS syntax introduced in FlexCel 7.1.1  could only be used in simple bands. The new "..ALIAS.." syntax doesn't have those limitations and can be used in all cases. Note that the old ALIAS syntax is still supported and you can use it for simple cases, but we recommend the new syntax for new development. Take a look at [Alias bands in the report designer's guide](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-designer-guide.html#alias-bands)

- **New "COUNT" parameter in &lt;#Aggregate> tag.** The [Aggregate Tag](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-tag-reference.html#aggregate) now accepts "Count" as aggregating method.

- **Bug Fix.** Now nested &lt;#aggregate> and &lt;#list> tags will be put in master-detail if they are related.

- **Bug Fix.** When inserting cell ranges with multiple rows used as data by pivot tables, the pivot table might not adapt correctly.

- **Bug Fix.** Sometimes when copying only format from cells, and the cells had only a column or row format, the format wouldn't be copied.

- **Bug Fix.** When exporting to HTML both headers and footers would be ignored if you specified THidePrintObjects.Header, and THidePrintObjects.Footer was ignored. Now footers will work with THidePrintObjects.Footer and THidePrintObjects.Header will only hide the headers.

- **Bug Fix.** Fixed issues with &lt;#evaluate> tag when it evaluates recursively

- **Bug Fix.** Some invalid third party xls files could fail to load.



## New in v 7.6.2 - June 2020


- **Bug Fix.** When adding a chart to a file via the API and immediately rendering it to PDF without saving it, the chart might not be rendered in the PDF file.

- **Bug Fix.** Previously the last row in "X" Bands in reports was deleted before the detail bands were inserted. This could cause unwanted behavior if the details shared the same rows as the master. Now last rows in X Bands will be removed after the details are inserted.

- **Bug Fix.** A fixed band inside a master-detail bidirectional report would behave as non fixed.

- **Bug Fix.** DbValue could raise Exceptions in some cases.



## New in v 7.6.1 - May 2020


- **Support for Rad Studio 10.4 Sydney.** Official support for Delphi 10.4

- **Improved conversion from strings to numbers.** Now FlexCel will behave more like Excel when converting strings to numbers, and convert for example the string "(1)" to the number -1.

- **Bug Fix.** Deeply nested array formulas could return N/A results in some corner cases



## New in v 7.6 - May 2020


- **Support for Rad Studio 10.4 Beta.** If you are in the Rad Studio 10.4 Beta, FlexCel setup will list it as an option for installing.

- **Support for rendering logarithmic charts.** Now FlexCel will render logarithmic charts to PDF or HTML.

- **When rendering pages to PDF and PNG, if an image or chart goes over the columns or rows in a page, now it won't overflow.** In previous FlexCel versions, if an image spilled over to the next page, it would also go over the last cell in the current page.

- **Now FlexCel will search in c:\Windows\Fonts and %localappdata%\Microsoft\Windows\Fonts for fonts when exporting to PDF.** Windows 10 version 1809 introduced the concept of "local fonts", that is fonts that are installed for the current user only. (see [https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/](https://blogs.windows.com/windowsexperience/2018/06/27/announcing-windows-10-insider-preview-build-17704/) ) So now FlexCel will search in the traditional Windows fonts folder and the current-user-font-folder by default. You can always change the behavior with the [GetFontFolder](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/GetFontFolder.html) event. See [the new section about fonts in Windows inside the PDF exporting guide](https://doc.tmssoftware.com/flexcel/vcl/guides/pdf-exporting-guide.html#fonts-in-windows)

- **Now FlexCel won't throw an Exception if a Font folder in the PDF FontFolder path doesn't exist.** Now when you specify multiple paths in the [GetFontFolder](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/GetFontFolder.html) event, FlexCel won't show an error unless none of those paths exist. In previous version, if you returned for example "c:\mypath1;c:\mypath2" and mypath2 didn't exist, FlexCel would shown an error. Now it will only show an error if both mypath1 and mypath2 don't exist. You can change this behavior with the new property [OnFontFolderNotFound](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/OnFontFolderNotFound.html)

- **Improved handling of chart gaps when there are null values.** In Excel 2003, an area chart would never have a gap: Null values would be considered 0. After Excel 2007, area charts can have gaps. FlexCel behaved like Excel 2003, never showing gaps for area charts. Now FlexCel will behave like Excel 2007 when reading newer xls/x files, while still behaving like 2003 when reading old xls files.

- **Bug Fix.** Sometimes when calling RenderObjects the border of a chart would not be exported to PDF or PNG.

- **Bug Fix.** Leader lines in stacked bar charts were wrong when the axis was reversed

- **Bug Fix.** Manually positioned labels in stacked bar charts were a little offset from their manual position.

- **Bug Fix.** Now FlexCel will draw a maximum of 10000 ticks per axis in charts, to avoid taking too long drawing too many ticks that aren't visible anyway.

- **Bug Fix.** Xlsm files containing macros and with sheet names starting with a number and bigger than 24 characters, could generate invalid files when saved in FlexCel.

- **Bug Fix.** Now FlexCel will validate when manually setting a sheet codename, that the name is ASCII and starts with a letter.

- **Bug Fix.** Bidirectional reports could fail to delete rows or columns in complex reports.

- **Bug Fix.** FlexCel would consider a protected range title containing a "?" invalid. This would prevent it from loading files that used "?" in protected ranges.

- **Bug Fix.** When manually installing FlexCel in Delphi XE, Delphi XE would raise an exception. Note that this is a fix only for manual installation: automatic installation worked fine.



## New in v 7.5.1 - April 2020


- **Bug Fix.** With some combinations of Delphi versions and platforms, you could get Access Violations when opening files in FlexCel 7.5. This was caused by a bug in the way Delphi handles method inlining, and it didn't happen in previous FlexCel versions. **If you installed FlexCel 7.5, please update.**



## New in v 7.5 - April 2020


- **Support for adding charts to a sheet with the API (xlsx files only).** A new method [AddChart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxFile/AddChart.html) will allow you to add a chart to a sheet in xlsx files, which you can then customize with other methods like [AddSeries](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/AddSeries.html). There is a new demo [Chart API](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/api/chart-api/index.html), and as usual, **APIMate** will show how to add a chart similar to one in Excel. Note that this method will work only in xlsx files, not xls.

- **New  methods SetTitle, SetOptions, SetChartLegend, SubchartCount, GetSeriesInSubchart, SetSeriesInSubchart and AddSubchart in ExcelChart.** The new method [SetTitle](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SetTitle.html) will allow  you to set the title of a chart. [SetOptions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SetOptions.html) will allow you to customize the properties of the chart. [SetChartLegend](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SetChartLegend.html) customizes the legend or adds a new one.  [SubchartCount](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SubchartCount.html) will tell you how many subcharts there are in the main chart.  [GetSeriesInSubchart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/GetSeriesInSubchart.html) and [SetSeriesInSubchart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SetSeriesInSubchart.html) allow you to read or set one series of one subchart. [AddSubchart](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/AddSubchart.html) adds a new subchart to the chart. Note that the methods are only for xlsx files.

- **New set method in the properties PlotArea, Background  in ExcelChart.** [PlotArea](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/PlotArea.html) can now change the properties of the plot area like the position or fill color. [Background](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/Background.html) can now change the background of the chart. Note that all the methods here will only work in xlsx files.

- **Now SetSeries and AddSeries, DeleteSeries work also in xlsx charts.** [SetSeries](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/SetSeries.html), [AddSeries](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/AddSeries.html) and [DeleteSeries](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsxChart/DeleteSeries.html) now work in xlsx charts the same as they work in xls charts.

- **Support for calculating the upcoming XLookup, XMatch, RandArray and Sequence functions.** FlexCel can now calculate the functions [XLookup](https://support.office.com/en-us/article/xlookup-function-b7fd680e-6d10-43e6-84f9-88eae8bf5929?ui=en-US&rs=en-US&ad=US), [XMatch](https://support.office.com/en-us/article/xmatch-function-d966da31-7a6b-4a13-a1c6-5a33ed6a0312?ui=en-US&rs=en-US&ad=US), [RandArray](https://support.microsoft.com/en-us/office/randarray-function-21261e55-3bec-4885-86a6-8b0a47fd4d33) and [Sequence](https://support.microsoft.com/en-us/office/sequence-function-57467a98-57e0-4817-9f14-2eb78519ca90) which are coming to Excel in July 2020.

- **Better chart rendering when there are date axis.** Now in some cases of date axis, FlexCel should render them better.

- **Support for importing bullet lists when importing html.** Now when calling [SetCellFromHtml](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/SetCellFromHtml.html), doing reports from html strings, or in general when importing html into a cell, FlexCel will import ordered and unordered bullet lists (&lt;ol> and &lt;ul>).

- **Preserving and adapting single cell mappings in XML Maps in xlsx files.** Now FlexCel will preserve and modify the references to single cells in an XML map inside an xlsx file.

- **Improved compatibility with invalid third party files.** Now FlexCel will ignore some parts of the xlsx file that should exist but might not when the xlsx files are manually edited. This will allow you to open those files anyway if there are no more errors besides that one.

- **Bug Fix.** FlexCel wasn't calculating conditional formats if the formulas defining the conditions were array formulas.

- **Bug Fix.** FlexCel could fail to process some files where a shape had an ending coordinate smaller than the starting coordinate.

- **Bug Fix.** When rendering charts you could get an index out of bounds in some corner cases.

- **FlexCel will ignore invalid themes when reading xls files.** Now when an xls file has an invalid theme, FlexCel will ignore it and just use the default theme instead of throwing an exception. This is the way Excel behaves.



## New in v 7.1.1 - January 2020


- **New __ALIAS postfix in named ranges allows multiple ranges to the same database.** Now if you need to define 2 names to the same dataset in the same sheet, you can name them like "__dataset1__ALIAS_SomeUniqueId" and "__dataset1__ALIAS_OtherUniqueId". Take a look at [Alias bands in the report designer's guide](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-designer-guide.html#alias-bands)

- **Bug Fix.** Sometimes in Android 32 or 64 bits you could get a BUS (10) error.

- **Bug Fix.** Effects for an image in the background of an image could be incorrectly saved. In some cases, this could cause Excel to crash.

- **Bug Fix.** When using a not standard row height for the whole sheet, FlexCel would create new rows to have automatic height, instead of having the standard row height for the sheet. This could confuse Excel.

- **Bug Fix.** FlexCel will now check that font sizes saved are between 1 and 409 points. Before it would let you save any font size, and invalid font sizes would crash Excel when opening the file.

- **Bug Fix.** In some corner cases charts saved by FlexCel inside xlsx files would fail to load.



## New in v 7.1 - December 2019


- **Android64 Support.** Now we support Android 64bit in Rio 10.3.3

- **Improved chart rendering.** Many small tweaks. We now support different line cap and join styles. The chart axis now goes above bar charts but below line charts. There is support for arrows at the end of lines in charts. The legend items draw a little larger to be more like Excel. And many more details.

- **Reports can now use nested properties in Aggregates, Filters, Sort and Master-details relationships.** Now in the config sheet you can filter or sort by a nested property, like for example sorting in the value of field1.field2.field3. Also you can use nested properties in relationships and in aggregates like &lt;#aggregate(max;table.field1.field2.field3)>

- **Now for reports you can set semi-absolute references in the config sheet.** Besides the old way to set semi-absolute references with [SemiAbsoluteReferences](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/SemiAbsoluteReferences.html), now you can change the setting directly in the config sheet. There is also a new [tip on what semi-absolute references are](https://doc.tmssoftware.com/flexcel/vcl/tips/semi-absolute-references.html).

- **Now you can use report expressions that call themselves recursively, as long as the recursion converges.** Now you can have a &lt;#tag> that depends on other &lt;#tag2> which at the end depends on &lt;#tag1> again, as long as it is not an infinite recursion. FlexCel now limits the number of recursions via the new property [ExpressionRecursionLimit](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/ExpressionRecursionLimit.html)

- **Improved recalculation speed and decreased memory usage.** We've fine tuned the calculation engine so it is faster and uses a less memory. We've also added 2 new methods: [StartBatchRecalcCells](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/StartBatchRecalcCells.html) and  [EndBatchRecalcCells](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/EndBatchRecalcCells.html). When you are doing multiple calls to  [RecalcCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/RecalcCell.html) you can speed up the recalculation by writing the calls between Start/EndBatchRecalcCell calls.

- **Breaking Change: Removed overload method TExcelFile.GetImage(Integer, string, TXlsImgType, TStream).** The method TExcelFile.GetImage(Integer, string, TXlsImgType, TStream) was confusing, because the ObjectPath (the second parameter), was always ignored. To use the objectPath, you needed to use [GetImage(Integer, string, TXlsImgType, TStream, Boolean)](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetImage.html#texcelfilegetimageinteger-string-txlsimgtype-tstream-boolean)  and set the last parameter to true. If you were passing an empty object path, then you could just call [GetImage(Integer, TXlsImgType, TStream)](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetImage.html#texcelfilegetimageinteger-txlsimgtype-tstream) 

- **The HTML engine can now parse &lt;font style> tags.** When setting a cell or a RichString from an HTML string, the old FlexCel could parse HTML like font color="red" or font size=3 but not font style="color:red;size:16px" Now both ways are supported.

- **Support for calculating BAHTTEXT function.** Now FlexCel can calculate BAHTTEXT.

- **Improved compatibility with invalid xlsx files.** Now FlexCel will ignore some missing parts in a corrupt xlsx file the same way Excel ignores them.

- **Updated to the latest version of Skia for Linux.** We've updated the Skia graphics engine we use in Linux to the latest.

- **Bug Fix.** FlexCel might not preserve comment backgrounds in xlsx files if the background was an image or texture.

- **Bug Fix.** FlexCel would nor correctly read or write left and right cell borders in strict xlsx files.

- **Bug Fix.** FlexCel was failing to render images which had an image filled background.

- **Bug Fix.** FlexCel could fail to open some files which didn't completely implement the xlsx spec but which Excel could open.



## New in v 7.0 - August 2019


- **Breaking Change: Support for rendering charts inside xlsx files.** We have fully rewritten the charting engine so it can now render charts inside xlsx files too. As charts inside xlsx files are completely different from charts inside xls files, this support meant that we had to modify some of the APIs to retrieve the chart information. If you are manually retrieving chart information like the color of the plot area or the title of a chart, some methods might have been moved or changed, so this is why this is a breaking change. But for most uses, nothing should break.

- **Support for Delphi Rio 10.3.2 including the new macOS 64 platform.** Now FlexCel can install in 10.3.2 and compile in macOS 64 apps.

- **Breaking Change: Improved compatibility with "Autosave" in Excel 2019.** When [OptionsCheckCompatibility](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/OptionsCheckCompatibility.html) is set in a file, Excel disables the Autosave function. To avoid accidentally writing this setting and thus diabling the Autosave function, now FlexCel will ignore this option by default and not write it to xlsx files. If you really want to save this setting to the file, you now also have to set [ForceUseOptionsCheckCompatibility](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/ForceUseOptionsCheckCompatibility.html) to true.

- **FlexCel will now generate "faux" bold and italics when exporting to PDF.** When exporting to pdf and the used font doesn't have italics or bold variants, FlexCel tries to simulate the styles by making the pen wider (for bold) or slanting the characters (for italics). The method used in older FlexCel versions  only worked when not embedding the fonts, but today most fonts are (and should be) embedded. This new FlexCel version creates "faux" italics or bold variants even when the fonts are embedded. To turn this feature off, you can use the property [UseFauxStyles](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/FallbackFonts.html) property in [FlexCelPdfExport](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport) .

- **Ability to specify different fallback fonts for italic, bold or bold-italic variants when exporting to PDF.** In addition to the existing [FallBackFonts](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/FallbackFonts.html) property in [FlexCelPdfExport](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport) we have now added 3 new properties: [FallBackFontsBold](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/FallbackFontsBold.html), [FallBackFontsItalic](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/FallbackFontsItalic.html) and [FallBackFontsBoldItalic](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TFlexCelPdfExport/FallbackFontsBoldItalic.html). If set to empty (the default) then FlexCel will keep looking for fonts in the usual way with FallBackFonts. But if you have fonts that have only regular, bold, italic or bold-italic variants, now you can specify different fall back fonts for each. So for example, you could use "Font1Bold" as a bold fallback, and "Font3Regular" as the regular fallback.

- **GetHtmlFromCell now can add the cell formatting to the resulting string.** The old version of [GetHtmlFromCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetHtmlFromCell.html) would return only the format of the rich string inside the cell, but not include the format of the cell itself. So if a cell was formatted as bold, but inside there was a plain "text" string, GetHtmlFromCell would return "text", and expect the text was hosted inside a table cell with style bold (&lt;td style="bold">text&lt;/td>). Now there is a new parameter "includeCellFormatting" that when true, FlexCel will return "&lt;b>text&lt;/b>" so you can use it outside formatted td tags.

- **Breaking Change: Support for semantic theme colors.** We added 4 new values for [TThemeColor](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TThemeColor.html) : Dark1, Light1, Dark2 and Light2. In the xlsx specification, there are 12 theme colors, which include "Dark1/2" and "Light1/2" variants. In Excel cells, the text color is "Dark" and the background color is "Light". But in drawings or charts, you can use 4 semantic colors: "Text1", "Text2", "Background1" and "Background2". While those colors are mapped Text->Dark and Background->Light, it is possible to manually edit an xlsx file and change the mapping. So now FlexCel differences between  [TThemeColor](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TThemeColor.html) (which now includes semantic colors) and  [TPrimaryThemeColor](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TPrimaryThemeColor.html) which includes only the 12 real theme colors and no semantic colors. Most of your code should stay the same, but if you are changing themes in code, you might need to replace some instances of TThemeColor by TPrimaryThemeColor. This is a compile-time breaking change: If your code compiles then nothing is broken. If your code doesn't compile anymore, you need to change TThemeColor by TPrimaryThemeColor where the compiler complains, and the code will keep working like before.

- **Breaking Change: Most properties in TDrawingRichString are now nullable.** Properties like bold or italics in a [TDrawingRichString](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TDrawingRichString/index.html) now can have a null value, which means that the value of the parent should be used. This change shouldn't affect most uses of TDrawingRichString, but if you were manually parsing DrawingRichStrings, you might now need to check if the nullable properties have a value before using them.

- **The &lt;#evaluate> tag in reports can now evaluate a string multiple times.** There is a new optional parameter in the [evaluate tag](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-tag-reference.html#evaluate) in reports that allows you to evaluate a string multiple times. This is useful if you store tags in the database itself. For example, if you have a field in the database named "Expression" with value "&lt;#other tag>", then &lt;#evaluate(&lt;#db.expression>;2>)> will evaluate first the value of expression, find out it is &lt;#other tag>, then evaluate again &lt;#other tag> and write the value of other tag in the cell.

- **Support for creating or reading xlsx files with uncompressed size bigger than 4 Gb.** FlexCel now uses the Zip64 file format automatically when creating xlsx files which won't fit in a standard zip container. It also can now read xlsx files saved with Zip64 file format.

- **New overloads for DeleteSheet allow to delete a sheet by its name or index.** There are now 2 new variants of [DeleteSheet](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/DeleteSheet.html). The first variant will let you delete a sheet given its name -- DeleteSheet("sheet1") --, and the other will let you delete n sheets since some index -- DeleteSheet(SheetIndex, NumberOfSheetsToDelete)

- **Improved bidirectional text handling.** We updated the Unicode bidi algorithm to the latest version, and added support for glyph mirroring and bracket matching algorithm. This should render right-to-left text in a way that is more compliant with the Unicode standard.

- **Improved drawing of autoshapes.** Excel 2007 changed the way in which it draws autoshapes in many small but visible ways. We made some tweaks in the autoshape algorithms and color handling routines to make autoshapes render even more like Excel 2007 and not Excel 2003.

- **Improved drawing of gradients and conversions from xls to xlsx.** We did a big rewrite of the gradient-handling code to better support the newer gradient styles in xlsx.

- **Improved drawing of patterns and conversions from xls to xlsx.** All pattern rendering code was reviewed and updated to better match Excel. Now every pattern style is exported to pdf/html/printed/etc.

- **Improved rendering in iOS, macOS, Android and Linux.** The rendering engines for CoreGraphics (used in iOS and macOS), SKIA (used in Linux) and Android have been updated to generate more accurate rendering of Excel files.

- **Improved support for Excel themes.** We've improved the theme engine to better handle files with wrong data in the themes. Now FlexCel can fix those files when you save them.

- **Improved compatibility when saving strict xlsx files.** While the strict xlsx files FlexCel created before were valid, now we create files that are more similar to what Excel creates when you save as strict xlsx.

- **Improved compatibility with invalid files created by third-party tools.** Now FlexCel can read files which have invalid cell references in the cell table, ignoring the reference completely as Excel does.

- **Improved conversion between strict and transitional xlsx files.** Now when preserving full parts of the xml of a strict or transitional file, FlexCel will convert the namespaces accordingly if you save as transitional or strict respectively.

- **Function Cell("filename") now returns the filename.** Now FlexCel can recalculate cell with Cell("filename"), which can be used to know the sheet where a cell is. Note that for security reasons, FlexCel won't return the folder there the file is, only the filename.

- **Breaking word in hyphens.** Now FlexCel will break words in hyphens when it has to fit multiple lines of text, same as Excel does.

- **Breaking Change: The Links property of TSheetSelector now is a readonly list of TSheetSelectorLink.** Now [Links](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TSheetSelector/Links.html) in TSheetSelector contains not only the name of the html sheet but also the name of the corresponding excel sheet. If you were using this property, you will need to  use Links[index].HtmlSheetName instead of Links[index]. Anew method  [GetHtmlSheetNameFromExcel](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TSheetSelector/GetHtmlSheetNameFromExcel.html) allows you to easily find the associated html sheet name from an Excel sheet name.

- **Bug Fix.** Some non visual characters like "right to left mark" were exported to pdf, even when they are invisible. Now they don't show in the generated pdfs.

- **Bug Fix.** FlexCel won't let you save files where tables have 0 rows of data, since that would become an invalid xlsx file. Now it will raise an exception if trying to save such file.

- **Bug Fix.** FlexCel won't let you enter empty array members anymore, like in the formula ={1,,2} which would create an xlsx file which could crash Excel. It will also automatically remove spaces before and after the element, so the formula ={ 1,  2,  3  } will be entered as {1,2,3}. Before this version, the formula ={ 1,  2,  3  } would be considered invalid.

- **Bug Fix.** When autofitting columns with line feeds (character 10) inside, FlexCel might fail to recognize them and try to fit everything in one line.

- **Bug Fix.** Arrows in lines were not scaling when printed or exported at a zoom different from 100%.

- **Bug Fix.** In html exporting, a cell which expanded over adjacent cells could cause the output to shift if there were hidden columns in the middle.

- **Bug Fix.** An unitialized variable when running reports could crash the report in rare cases

- **Bug Fix.** When exporting a file as HTML with tabs for sheets and there were hidden sheets between sheets, the links in cells to a different tab could be incorrect.

- **Bug Fix.** Some hyperlinks in xls files could return an empty string when read, even if they had data.

- **Bug Fix.** Lines with 0 width were not showing in SVG files.

- **Bug Fix.** Sometimes when copying cells between files the indexed colors could be converted to similar but not equal  RGB colors.

- **Bug Fix.** When using the SKIA/Android graphic stack some lines in the charts could appear not connected.

- **Bug Fix.** FlexCel was not exporting correctly to CSV when using Big-Endian UTF16 encoding.



## New in v 6.26 - March 2019


- **In Reports now you can reference tables which include dots by writing &lt;#[db.something].field>.** Now you can use square brackets in both the table name or field name to reference tables or fields which include dots. This is useful especially for reports from classes as shown in the new [Advanced  Reports From Lists example](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/reports/advanced-reports-from-lists/index.html).

- **Improved compatibility with LibreOffice/OpenOffice.** LibreOffice/OpenOffice can't at the time of this writing understand indexed colors inside xlsx files. Now we introduce a new property (false by default) named  [XlsxCompatibilityConvertIndexedColorsToRGB](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/XlsxCompatibilityConvertIndexedColorsToRGB.html) which when true, will make FlexCel convert the indexed colors to RGB colors when saving xlsx files. Set it to true if you have xlsx files with indexed colors and you want them  to be compatible with Libre/OpenOffice.

- **Now FlexCel won't throw an exception when reading custom properties in an xls file if the values of the property aren't defined.** Either because of corruption or because they were created with a tool that created wrong files,  some xls files might end up having a custom property but no value associated with them. FlexCel was throwing exceptions when you tried to read the properties of those files, but that didn't allow you to get other properties which might be set correctly. So now FlexCel will just ignore those errors.

- **Bug Fix.** The setup wasn't compiling c++ headers for Android and iOS in Rad Studio Rio.

- **Bug Fix.** Workaround a GDI+ bug which could cause Internal errors when using small path gradients.

- **Bug Fix.** FlexCel would fail to read xlsx files with formulas that contained unknown user-defined functions that returned a reference type.

- **Bug Fix.** FlexCel will now render labels in a 100% stacked chart as the values, not the percent in the charts.

- **Bug Fix.** If an xlsx file contained negative offsets to a shape, FlexCel could render the shape incorrectly.

- **Bug Fix.** FlexCel will now render labels in stacked charts more like Excel renders them.

- **Bug Fix.** When rendering charts, if the axis was reversed and the labels were aligned to the right, FlexCel would render them to the left and vice-versa.



## New in v 6.25 - February 2019


- **New parameter in ATLEAST tag in reports allows for the number of rows of a dataset to be multiple of a number.** Now when using [ATLEAST](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-designer-guide.html#ensuring-a-table-has-at-least-n-records) you can specify that the number of rows must be a multiple of some number. That is, that the dataset must have for example 20, 40, 60... rows but not 30 or 45. Take a look at the new [Fixed Footer demo](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/reports/fixed-footer/index.html)

- **Improved handling of invalid "," in numeric formats.** A comma in a numeric format means "thousands separator" if it goes after the 3rd digit, like in "#,000". But when a comma is at the end of the format, it means scale: A format like "0," means divide the number by 1000. FlexCel already handled those cases correctly, but there are some "impossible" cases like "0,0" which are not actually valid but might be saved to xlsx files. FlexCel was interpreting that the "," in some of those cases meant scale, while for the same cases Excel was interpreting "thousands separator". Now we should behave like Excel even in the invalid cases.

- **Improved rendering of TFlexCelPreview in FireMonkey in Windows when in High dpi.** While FlexCelPreview already handled most high-dpi cases correctly, it was failing to render correctly in Windows when using FireMonkey. Now it should work correctly as in the other cases.

- **Bug Fix.** FlexCelPreview wasn't working correctly in Android. Some changes in the Android API made some methods used by FlexCelPreview deprecated. Now we call the newer methods.

- **FlexCel could fail when rendering cells with more than 32000 characters.** A cell in Excel is limited to 32767 characters, but a string in GDI+ is limited to 32000 characters. So if a cell had between 32000 and 32767 characters, FlexCel would raise an Exception when rendering the file because GDI+ would fail to render the string. Now it should render correctly.

- **Improved APIMate.** ApiMate was reporting code that wouldn't compile for cells with hyperlinks.



## New in v 6.24 - January 2019


- **The INDIRECT function can now understand structured references in tables.** Now FlexCel can calculate formulas where INDIRECT references a table. For example if you have a table named "Table1", FlexCel will now understand a formula like =SUM(INDIRECT("Table1[Column1]"))

- **Breaking Change: Cell indent is now printed and rendered to pdf/images proportional to the print scale.** Before this version, FlexCel behaved just like Excel and kept the cell indent always the same no matter the print scale. Now we behave in a more logical way, and if the print scale is 50%, the cell indents will be 50% smaller. If you want to revert to the old behavior (which is how Excel behaves), there is a new property [CellIndentationRendering](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/CellIndentationRendering.html) which allows to control this behavior and revert it back to what it was. For more information read the new [section about cell indentation in the API guide](https://doc.tmssoftware.com/flexcel/vcl/guides/api-developer-guide.html#cell-indentation).

- **Breaking Change: TFlexCelDocExport now uses a different way to share files in Android.** If you have existing apps using FlexCelDocExport, make sure to review them and add a provider to them so FlexCelDocExport will keep working. This was needed so new Android apps can comply with the new Play store rules. Please read the [Android guide](https://doc.tmssoftware.com/flexcel/vcl/guides/android-guide.html#sharing-files) for more information.

- **The examples for Android show a newer way to share the documents.** The revised examples for Android now use a sharing method that is compatible with Android Nougat or newer. TFlexCelDocExport will now use the new sharing method in Android. There is new documentation available at the [Android guide](https://doc.tmssoftware.com/flexcel/vcl/guides/android-guide.html#sharing-files)

- **New methods SetRange3DRef and TrySetRange3DRef in TXls3DRange.** The new methods  [SetRange3DRef](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/SetRange3DRef.html) and [TrySetRange3DRef](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/TrySetRange3DRef.html) allow you to set a 3D range from a string like "=Sheet1:Sheet2!A1:A3"

- **DbValue in reports now supports fields with dots.** DbValue tag in reports will now work with fields with dots like "data.value"

- **Bug Fix.** When deleting columns the data validations formulas could be adapted wrong.

- **Bug Fix.** When a line in rich text inside a text box had a length 0 (an empty line), the font might not be preserved for that line.

- **Bug Fix.** FlexCel considered some special characters like "°" in a name to be invalid when they are not. This could cause that opening and saving an xlsx file with names like that would make Excel crash opening the file.



## New in v 6.23 - November 2018


- **Delphi 10.3 Rio Support.** FlexCel now supports Delphi 10.3 Rio.

- **New methods UnshareWorkbook and IsSharedWorkbook in TExcelFile.** The method [UnshareWorkbook](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/UnshareWorkbook.html) allows you to remove all tracking changes from an xls file. (FlexCel doesn't preserve tracking changes in xlsx files). [IsSharedWorkbook](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/IsSharedWorkbook.html) allows you to know if an xls file is a shared workbook.

- **New method PivotTableCountInSheet in TExcelFile.** The method [PivotTableCountInSheet](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/PivotTableCountInSheet.html) returns the number of pivot tables in the active sheet.

- **Support for calculating function RANK.AVG.** Added support to calculate the Excel function Rank.AVG which was introduced in Excel 2010. See [supported excel functions](https://doc.tmssoftware.com/flexcel/vcl/about/supported-excel-functions.html#added-functions-in-excel-2010).

- **Now you can find see the call stack in circular formula references when you call RecalcAndVerify.** Now [RecalcAndVerify](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.XlsAdapter/TXlsFile/RecalcAndVerify.html) will report the call stack that lead to a cell recursively calling itself, making it simpler for you to track those down in complex spreadsheets. Take a look at the modified [Validate Recalc demo](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/api/validate-recalc/index.html) with a file with circular references to see how it works.

- **The installer should now install anyway even if your MSBuild command line is longer than 32000 characters.** FlexCel will now not check for invalid command lines and install anyway even if your Delphi installation has a search path which is too big.

- **Bug Fix.** Some xlsx files with legacy headers could fail to load.

- **Bug Fix.** The function IFNA could in very rare corner cases return #N/A if its first parameter was #N/A instead of returning the second parameter.

- **Bug Fix.** There could be an error when copying sheets between workbooks and the sheet copied had a shape with a gradient.

- **Bug Fix.** Floating point numbers that were either infinity or not-a-number were saved wrong in the files and Excel would complain when opening them. Now they will be saved as #NUM! errors. Note that this only happened if you set a cell value explicitly to Double.NAN or Double.Infinity. Formula results which were infinity or nan were already handled fine.



## New in v 6.22 - October 2018


- **Support for Excel 2019.** Because we support Excel 365 and changes in Excel 2019 are a recollection from the changes in office 365 from 2016 up to now, FlexCel already supported Excel 2019. For example, support for recalculating the new functions introduced in Excel 2019 was introduced by [FlexCel 6.7.16](https://doc.tmssoftware.com/flexcel/vcl/about/whatsnew.html#new-on-v-67160---march-2016) back in march 2016. But this new FlexCel version adds a new TRecalcVersion.Excel2019 enumeration which will [avoid the question about saving for changes when closing the file](https://doc.tmssoftware.com/flexcel/vcl/guides/api-developer-guide.html#avoiding-the-want-to-save-your-changes-dialog-on-close). It also adds a "v2019" enumeration to TFileFormats, which allows you to specify you want the file to identify itself as office 2019 and comes with empty 2019 files to be created with NewFile. Empty 2019 files are virtually identical to empty 2016 files, but the colors "Accent1" and "Accent5" in Excel 2016 are swapped to correspond to "Accent5" and "Accent1" respectively in Excel 2019.

- **Reports now can use tables as datasources.** Now you can use Excel tables as sources for reports. Take a look at the new [Tables as datasources](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/reports/tables-as-datasources/index.html) demo and the [section about excel tables in the Report designers guide](https://doc.tmssoftware.com/flexcel/vcl/guides/reports-designer-guide.html#excel-table-bands).

- **New method to rename tables.** The new method [RenameTable](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RenameTable.html) can rename a table to a newer name, changing all references in formulas to the new name.

- **New Debug mode for Intelligent Page Breaks.** Now you can use the property [DebugIntelligentPageBreaks](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/DebugIntelligentPageBreaks.html) in a report, or the methods [DumpKeepRowsTogetherLevels](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/DumpKeepRowsTogetherLevels.html) and [DumpKeepColsTogetherLevels](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/DumpKeepColsTogetherLevels.html) in the API to debug how intelligent page breaks are working. Look at [intelligent page breaks in the API Guide](https://doc.tmssoftware.com/flexcel/vcl/guides/api-developer-guide.html#intelligent-page-breaks) for more information on how to use the feature.

- **Better drawing of conditional formats at very low or high zoom levels.** Now icons and databars in conditional formats dynamically adjust the margins to look better at high or low zoom levels.

- **Bug Fix.** Cell indent was not being considered when autofitting rows or columns.

- **Bug Fix.** FlexCel wouldn't let you rename a sheet to the same name but with different upper or lower cases.

- **Bug Fix.** CountIF, CountIFs and similar xIf/xIfs functions could return ERRNA if one of the conditions was an unknown user function, instead of returning 0 as Excel does.

- **Bug Fix.** The function Rank.EQ was ignoring cells with errors while Excel returns the first cell with error if any cell in the range has an error.

- **Bug Fix.** Inside a &lt;#preprocess> section of a report a &lt;#delete row> or &lt;#delete column> tag could end up deleting the wrong column.

- **Bug Fix.** Error when calculating What-If tables that had their variables in a different sheet.

- **Bug Fix.** When deleting rows in reports with multiple levels of intelligent page breaks the engine could calculate more page breaks than necessary.

- **Bug Fix.** FlexCel will now validate that a table isn't named the same as a defined name or vice-versa, to avoid creating invalid Excel files.

- **Bug Fix.** When rendering a file to pdf or images FlexCel could pick the wrong normal font in very rare cases.

- **Bug Fix.** Reports in DataSets with primary keys of type GUID could throw a null reference exception if the master key didn't exist for a detail instead of outputting an empty row.

- **Bug Fix.** APIMate could report code that wouldn't compile for embedded xml content.



## New in v 6.21.6 - September 2018


- **Updated Skia libraries  to the latest.** The Skia libraries used in Linux have been updated to the latest version at release time.

- **Improved Linux support.** Many small bug fixes and updates to the Delphi Linux support.

- **Bug Fix.** FlexCel would fail to load "Strict Open XML files" with formulas which returned dates.

- **Bug Fix.** FlexCel could crash when rendering xls files with rare images.



## New in v 6.21.5 - August 2018


- **Bug Fix.** FlexCel could fail to parse complex structured references in tables.

- **Bug Fix.** Formulas that referred to different files could refer to the wrong sheet on those linked files in some rare cases.

- **Bug Fix.** the IFERROR function could give a #VALUE! error in some cases when used chained with other functions.

- **Bug Fix.** Tables with columns in more than one line could cause Excel to show an error.

- **Bug Fix.** There could be a Nullable type error when loading files with specific combo boxes.



## New in v 6.21 - July 2018


- **Bug Fix.** If a "rows to repeat at top" or "columns to repeat at left" range was outside the print area, FlexCel would ignore it, while Excel will use it anyway. Now FlexCel behaves like Excel and uses the repeating range even if it is outside the print area.

- **Bug Fix.** When in R1C1 mode, full ranges expanding more than 1 row or column like for example Sheet1!3:5 could be returned as Sheet1!5 only.

- **Bug Fix.** Sometimes cells formatted as "center on selection" were not rendered when exporting them to pdf or html.

- **Bug Fix.** When hiding a column without a given width and the default column width was different from the Excel default, the column wouldn't be hidden when saving as xls.

- **Bug Fix.** There could be an error in ClearSheet with some special images.

- **ApiMate now reports hidden sheets.** ApiMate will now tell you how to hide sheets.

- **Improved chm help.** The chm help shipped with FlexCel could show javascript errors in some Windows versions.



## New in v 6.20 - June 2018


- **Full support for reading and writing Data Connections in xlsx files.** Now you can use the new methods [GetDataConnections](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetDataConnections.html) and [SetDataConnections](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetDataConnections.html) for reading and writing the data connections in xlsx files. As usual, APIMate will show you the commands needed to enter new DataConnections.
Note that the new methods only work in xlsx files, not xls, and there is no support for refreshing data queries from FlexCel. Only to read or write connections.

- **Improved performance with thousands of merged cells.** We rewrote the merged cell handling engine to make it faster and work better when there are thousands of merged cells.

- **Breaking Change: Improved chart rendering.** Now FlexCel recalculates the size of the legends of the charts if those are docked to the top, bottom, right, left or top-right. So if the size of the series change, the legend box and the rest of the chart will adapt.
There are also other small tweaks in the chart rendering engine to make xls charts more faithful to what Excel shows. **Note**: The Excel chart engine has changed a lot since the Excel 2003 times, and Excel 2003 doesn't display charts exactly as Excel 2016. We can't make it work both ways, so this update makes the chart rendering more like Excel 2016. If you were rendering old files and relied in the exact position of the legend, this update might move the position of the legend a little, to position it how Excel 2016 would and not how Excel 2003 would. This is why it is a breaking change.

- **New overloads for methods SetCellFromString and GetStringFromCell now accept cell references.** The methods [SetCellFromString](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetCellFromString.html) and [GetStringFromCell](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetStringFromCell.html) now can use references like A1 or "Sheet1!B3". This is a shortcut in using a [TCellAddress](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TCellAddress/index.html) object to get the row and column from the reference.

- **New overload for method TPartialExportStart.SaveCss which allows to save the css without the &lt;style> and &lt;/style> tags.** There is now an overload of [TPartialExportState.SaveCss](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Render/TPartialExportState/SaveCss.html) with a parameter that allows to get the inner html of the classes definition, without the &lt;style> and &lt;/style> enclosing tags.

- **Bug Fix.** Memory leak with color scale conditional formats when calling InsertAndCopyRange.

- **Bug Fix.** There could be an error in GDI+ when exporting emf images to html

- **Bug Fix.** The [Copy and Paste](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/api/copy-and-paste/index.html) demo wasn't correctly copying the data in TEXT format. Now it shows the correct way to copy text to the clipboard.

- **Bug Fix.** Setup wasn't generating hpp files for iOS and Android with Delphi Tokyo.



## New in v 6.19.5 - May 2018


- **Now functions CUMIPMT and CUMPRINC are supported when recalculating.** Now FlexCel can recalculate the functions [CUMIPMT](https://support.office.com/en-us/article/cumipmt-function-61067bb0-9016-427d-b95b-1a752af0e606) and [CUMPRINC](https://support.office.com/en-us/article/cumprinc-function-94a4516d-bd65-41a1-bc16-053a6af4c04d)

- **New methods GetTokens and SetTokens in ExcelFile allow you to parse arbitrary text.** The new methods [GetTokens](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetTokens.html) and  [SetTokens](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetTokens.html) allow you to parse any text into tokens and then convert those tokens back into a string. Those methods complement the existing [GetFormulaTokens](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetFormulaTokens.html) and [SetFormulaTokens](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetFormulaTokens.html)

- **The XlsChart object now returns the 3D properties for xls charts.** Now you can read the 3D properties in charts inside xls files.

- **Improved Excel 95 compatibility.** Now FlexCel can read some Excel 95 files which would throw errors before.

- **Now FlexCel preserves "new style" sheet and workbook protections in xlsx files.** Both FlexCel and Excel use an old algorithm to compute sheet and workbook protections, and they both keep doing it this way as it is the only way to port the protections between xlsx and xls files. But some third-party generated files could have a newer style of protections which are incompatible with xls and FlexCel wasn't understanding them. Now FlexCel will preserve those new style protections in xlsx files too. The new style protections will be lost if you save as xls, but that happens in Excel too.

- **When wrapping text, now FlexCel recognizes different kind of unicode spaces.** Now other spaces in addition of character 32 are used as separators when rendering the file and wrapping the text. Note that not breaking spaces (char 160) are still not used as separators as they aren't supposed to break a line.

- **Bug Fix.** SetCellFormat with ApplyFormat could format the cells wrong if the cells were empty and there was column or  row format applied.

- **Bug Fix.** Sometimes when copying sheets form different files, some named ranges would not be copied.

- **Bug Fix.** Khmer text could be rendered wrong is some rare cases.

- **Bug Fix.** When exporting to pdf you could get an error if a character didn't exist and fallbackfonts was empty.



## New in v 6.19.0 - March 2018


- **Support for Khmer language when exporting to pdf.** The PDF engine in FlexCel now includes a Khmer shaper which is able to correctly create Khmer documents, as long as the Khmer fonts you are using are OpenType (that is they contain GSUB and GPOS tables).

- **Reduced memory usage when exporting.** Exporting to PDF and SVG were tweaked to consume less memory in high-performance environments where many threads are exporting at the same time. Also the performance of the pdf engine was improved.

- **Images made transparent with Excel now are converted between xls and xlsx files.** Now FlexCel will convert the transparent color parameter between xls and xlsx files.

- **Bug Fix.** In some cases after copying rows, then deleting sheets and then inserting or deleting rows, the formula bounds cache could be invalid and formulas would fail to update in the lase deleting of the rows.

- **Bug Fix.** The round function now behaves more like Excel and not like C# in some border cases.

- **Bug Fix.** A file with too many objects with the same name could cause an stack overflow.

- **Bug Fix.** Formulas with intersections of a name with a 3d range would be interpreted as #name instead of the correct formula.

- **Bug Fix.** In some invalid cases the indirect function would throw exceptions that would be later processed. While the result was still ok, those exceptions could slow down a lot recalculation in a file with thousands of formulas.



## New in v 6.18.5.0 - January 2018


- **New convenience methods SetCellValue(cellRef, value) and GetCellValue(cellRef).** The new methods [SetCellValue(cellRef, value)](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetCellValue.html#excelfileSetcellvaluestring-object) and [GetCellValue(cellRef)](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetCellValue.html#excelfilegetcellvaluestring) allow you to set or get a cell value directly from a text reference like "A1" without having to use a [TCellAddress](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TCellAddress/index.html) class.

- **Support for shape connectors in xlsx.** Now FlexCel will preserve connections between shapes in xlsx, and convert them from xls to xlsx and viceversa. We've also added the properties [IsConnector](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/IsConnector.html)  [StartShapeConnection](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/StartShapeConnection.html) and [EndShapeConnection](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/IShapeProperties/EndShapeConnection.html) to allow you to enter connections with the API. As usual, APIMate will tell you the code needed to add a connector from an Excel file.

- **Bug Fix.** The VLOOKUP and HLOOKUP functions now support wildcards (* and ?) in search strings.

- **Improved compatibility with invalid files generated by third-party tools.** Some xlsx generators can write invalid column widths. Now when exporting to html/pdf, FlexCel will consider those widths as default (like Excel does) and not 0 (as it used to do).

- **Bug Fix.** FlexCel could fail to parse some structured references in tables.

- **Bug Fix.** When calculating UDFs and there were errors in the arguments, FlexCel could in some cases return #ERRNAME! instead of evaluating the UDF.

- **Bug Fix.** In some files the calculated height for items inside Forms Listboxes was too big.

- **Bug Fix.** FlexCel failed to read custom document properties saved in UTF16.

- **Bug Fix.** Reports with [DeleteEmptyBands](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Report/TFlexCelReport/DeleteEmptyBands.html) = TDeleteEmptyBands.ClearDataOnly would not clear text inside textboxes or hyperlinks.

- **Bug Fix.** In some bidirectional reports with report.DeleteEmptyBands = TDeleteEmptyBands.MoveRangeUp the tag text was not erased.



## New in v 6.18.1.0 - December 2017


- **Bug Fix.** Zoom was not working correctly in the TFlexCelPreviewer component. This was a regression bug introduced in FlexCel 6.18.



## New in v 6.18.0.0 - December 2017


- **Support for Rad Studio 10.2.2.** Rad Studio 10.2.2 introduced some changes that prevented FlexCel from compiling.

- **Support for default CryptoAPI xls encrypted files.** Now FlexCel can read and write xls files encrypted with the CryptoAPI encryption. This is the default encryption algorithm for files created by Excel 2003 or newer. With this addition, all modes and encryption algorithms in both xls and xlsx are now supported.

- **Full support for manipulating XML Mappings in xlsx files.** Now XML Mappings will be preserved when opening and saving xlsx/m files, and there are two new commands in the API to set them or read them with code. The new commands are [GetXmlMap](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/GetXmlMap.html) and [SetXmlMap](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetXmlMap.html) . As usual, APIMate will show how to use `SetXmlMap`. **Note**: The new API only works in xlsx/x files, not xls. Xml mappings inside xls files will still be preserved when opening and saving xls files, but not converted between xls and xlsx.

- **Bug Fix.** Images made transparent with Excel tools might not preserve their transparency when saved as xlsx.

- **Bug Fix.** When rendering shapes with semi-transparent gradients to PDF or SVG the gradients were exported as fully opaque.

- **Bug Fix.** Files with table slicers saved by FlexCel might not open in Excel 2013. (They already worked fine in Excel 2016, and Excel 2010 doesn't support table slicers).

- **Bug Fix.** Rotated shapes inside groups in xlsx files could be rendered wrong.

- **Bug Fix.** Groups that were flipped horizontally or vertically weren't flipped when rendering. Objects inside were flipped, but the groups themselves weren't.

- **Bug Fix.** Filled polygons could be exported wrong to PDF in  some border cases.

- **Bug Fix.** Filled polygons could be exported wrong to images with the SKIA backend used in Linux.

- **Bug Fix.** Legacy system colors in drawings inside xls files could be rendered as transparent instead of the correct color in border cases.

- **Bug Fix.** Xlsx files with complex gradients where the stops were not sorted could cause invalid PDF files.

- **Bug Fix.** Textboxes with more than 8224 characters would corrupt the file when saved as xls.

- **Bug Fix.** Very complex images could cause a GDI+ error when previewing them.



## New in v 6.17.5.0 - November 2017


- **Bug Fix.** This release workarounds a bug in Delphi XE4 and XE5 which made FlexCel crash when rendering in those Delphi versions. If you have FlexCel 6.17.4 and aren't using XE4 or XE5, then you might skip this update.



## New in v 6.17.4.0 - November 2017


- **Breaking Change: Subtotal command allows more customization.** Now the [Subtotal](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/Subtotal.html) command provides more parameters in the callbacks to allow for more customization. In addition, by default it will write a better text for non sum aggregates (like for example "Customers Average" instead of "Customers Total" if you are using the Average to aggregate). There is also a new example on how to use the command. **Note**: This is a breaking change if you are using the callbacks since now the callbacks have more parameters. But it is easy to fix at compile time, just add those parameters to the callbacks and recompile.

- **New SubtotalDefaultEnglishString command.** Now the [SubtotalDefaultEnglishString](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SubtotalDefaultEnglishString.html) provides the string used by the different aggregate functions used in [Subtotal](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/Subtotal.html) . You can use this method as a parameter to subtotal to calculate the grand total and subtotal labels.

- **Ability to copy OLE objects between different files while using xlsx file format.** Now the restriction that you can't copy sheets from one file to another if they have embedded OLE object has been removed for xlsx files. It is still not possible to copy sheets between different files with embedded OLE objects in xls.

- **Ability to read custom document properties in xls files.** Up to now FlexCel could only read custom document properties in xlsx files. Now it can also read them in xls files. And now custom properties are migrated from xls files to xlsx too.

- **Better handling of URL encoding when encoding some filenames.** Now some filenames containing some characters like "#" will be correctly encoded when linked from FlexCel. The events that allow you to manually define the links have a new parameter "UrlNeedsEncoding" which you can set to false to avoid all encoding by FlexCel if you provide an already encoded URL to the event.

- **Bug Fix.** The **Last print time** document property wasn't read in xlsx files.

- **Bug Fix.** There was an error when linking **localized** projects using FlexCelReport.

- **Bug Fix.** When copying cells from one file to another autofilters would be copied even if they were not in the range being copied.

- **Bug Fix.** Formulas referencing sheets which could be interpreted like a R1C1 cell reference (like "R3C5") were saved without quotes in the sheet name, and thus became invalid formulas.

- **Bug Fix.** In some very complex bidirectional reports with sorting in the template the fields might end up not being sorted correctly, and some might appear twice.



## New in v 6.17.3.0 - October 2017


- **New TFlxNumberFormat.PercentCount method.** The new method [TFlxNumberFormat.PercentCount](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TFlxNumberFormat/PercentCount.html) allows you to know how many non escaped % symbols are in a format string.

- **Better display of negative zero numbers.** Now a negative number that displays as zero like "-0.001" formatted with a "0.0" format string will display as "0.0" and not "-0.0"

- **Better handling of the Windows Font folder.** Now in we use a different set of APIs to retrieve the Windows font folder and fallback to other methods if the OS is XP or Server 2003 where those APIs are not supported.



## New in v 6.17.2.0 - October 2017


- **Better support of machine locale formats.** Before this version, whenever you used a "machine dependent" date numeric format (those shown with * in Excel), FlexCel would use always 2-digit months, 2-digit days and 4-digit years. (as in 01/02/2000). Now it can use single digits for days and months, and 2 digits for years (as in 1/2/00) if your machine locale is set to a format that uses those.

- **Improved xls chart rendering.** Now series which are in hidden columns or rows won't count as series at the moment of drawing the chart, to better copy Excel behavior. Before this version those series would appear empty, but still take space in the chart.

- **Improved compatibility with invalid 3rd party xlsx files.** Now FlexCel can open files where the case of the files inside the container is incorrect. This happens with files generated by  "1C" database and might happen with other 3rd party files.



## New in v 6.17.1.0 - September 2017


- **Bug Fix.** The packages in 6.17 could cause an Access violation. If you installed 6.17 please update to 6.17.1.



## New in v 6.17.0.0 - September 2017


- **Full Support for Excel tables in xlsx files.** This  release completes the support for tables in the FlexCel API introduced in 6.11.
   * Tables are now exported to PDF/HTML/SVG/Images and printed with all the table formatting including banded columns and rows, etc. All formatting is supported.
   * Now FlexCel can recalculate the [structured references](https://support.office.com/en-us/article/Using-structured-references-with-Excel-tables-f5ed2452-2337-4f71-bed3-c8ae6d2b276e) used in tables. Everything is supported, from simple references like Table1[@column] to references in tables from another file. (for external table references you need to create a [Workspace](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TWorkspace/index.html) )
   * Complete API for adding, deleting or modifying tables with code. APIMate was modified to show how to use the new things in the API.
   * API for adding, deleting or modifying custom table styles. APIMate shows how to enter table styles with code.

- **Support for reading and writing Strict Open Xml files.** Now FlexCel can read and write [Strict Open XML spreadsheets](https://www.loc.gov/preservation/digital/formats/fdd/fdd000401.shtml). The default is to save to strict xml only if you opened a strict xlsx file and saved it, in the other cases we fall back to the standard transitional xlsx. There is a new property [StrictOpenXml](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/StrictOpenXml.html) which you can set to force saving as strict xlsx, and read to know if the file you opened was strict xlsx.

- **Ability to add autoshapes to charts.** Now the existing method [ TExcelFile.AddAutoShape](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/AddAutoShape.html) works also in chart sheets, and there is a new method  [ TExcelChart.AddAutoShape](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelChart/AddAutoShape.html) that allows to add shapes to charts embedded inside a sheet.

- **FlexCel will now preserve embedded OLE objects in xlsx files.** Now FlexCel will preserve embedded OLE documents (like for example a word document) in xlsx files.

- **Improved performance in reports with thousands of hyperlinks.** Now FlexCel is much faster dealing with thousands of hyperlinks in reports.

- **&lt;#row height> and &lt;#column width> tags in reports now accept expressions.** Now you can write something like &lt;#row height(&lt;#someexpression>)> where expression will be calculated at the moment of running the report.

- **Now FlexCel converts strings with timestamps to dates more like Excel.** In Excel you can write a string with an invalid timestamp like "3:61" (3 hours 61 minutes, which is 4 hours 1 minute) and it will be accepted by the system. FlexCel was rejecting those timestamps, but now it accepts them just like Excel.

- **Support for #GETTING_DATA error in TFlxFormulaErrorValue.** The enumeration [TFlxFormulaErrorValue](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TFlxFormulaErrorValue.html) now contains a new ErrGettingData member which corresponds to the type in Excel. Also [Error.Type](https://support.office.com/en-us/article/ERROR-TYPE-function-10958677-7c8d-44f7-ae77-b9a9ee6eefaa) function will return 8 for this error. Note that Excel doesn't save this error in xlsx files (it saves #N/A instead), but it does save it in xls files. FlexCel preserves it in both.

- **Better support for comments in xlsx file in high dpi.** The size of the comments is preserved better now when ScreenScaling is > 0

- **Now TExcelFile.RenderObject can render shapes inside groups and use an objectPath parameter to specify the name of the object to render.** There are new overloads in [ TExcelFile.RenderObjects](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RenderObject.html) and [ TExcelFile.RenderObjectAsSVG](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RenderObjectAsSVG.html) that take an **objectPath** parameter. This allows you to render an individual shape inside a group instead of the full group, and also to specify directly the name of the shape to render as in `xls.RenderObject(1,"@objectname")`

- **Reduced memory usage when loading fonts for exporting to PDF.** We've optimized the pdf font engine so it uses less memory when loading the fonts.

- **Support for returning arrays with the INDIRECT function.** When doing a *Sum*, *SumIf* or N of an *Indirect* function which returned an array, FlexCel worked like Excel 2003 or older and only used the first value of the array. Now it uses the full array in *SumIf* and N like Excel 2007 or newer, and in *Sum*, like Excel 2010 or newer. This allows you to write formulas like the ones mentioned here: [https://www.pcreview.co.uk/threads/indirect-function-limitations.1750391/](https://www.pcreview.co.uk/threads/indirect-function-limitations.1750391/) 
Note that this formula behavior is exclusive to Excel 2010 or newer: Neither LibreOffice or Google docs implement it.

- **All examples available in Github.** Now besides being available with the setup and at the [documentation site](https://doc.tmssoftware.com/flexcel/vcl/samples/index.html) the examples are also available on [Github](https://github.com/tmssoftware/TMS-FlexCel.VCL-demos)



## New in v 6.16.0.0 - August 2017


- **User defined formats in reports.** Now you can define a function in code that will format the cells depending on complex rules. Take a look at the new [User Defined Formats demo](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/reports/user-defined-formats/index.html) to see an example on how to use them.

- **Now when signing PDFs, FlexCel will mark the generated files as requiring Acrobat 8.** Due to known vulnerabilities in SHA1, signing with SHA1 is deprecated. So now the FlexCel signing demos have been modified to use SHA512. As SHA512 requires Acrobat 8 or newer, now the files will be marked as requiring Acrobat 8 or newer. Note that older acrobat versions will still be able to see the file, but they won't validate the signatures.

- **Simplified support for signing PDFs in Windows.** Now we use CryptoAPI to sign pdfs in Windows, without you needing to implement your own signing classes. An example on how to sign a document has been added to the demos.

- **Added recalculation support for new functions.** Added support for [CEILING.MATH](https://support.office.com/en-us/article/CEILING-MATH-function-80f95d2f-b499-4eee-9f16-f795a8e306c8) , [FLOOR.MATH](https://support.office.com/en-us/article/FLOOR-MATH-function-c302b599-fbdb-4177-ba19-2c2b1249a2f5) functions added in Excel 2013.

- **Improved behavior of CEILING/FLOOR functions.** Now the existing CEILING, FLOOR, ISO.CEILING, CEILING.PRECISE and FLOOR.PRECISE functions are calculated more in the way Excel uses them, with a higher precision to prevent rounding errors like 1.00000...00001 to be rounded up to 2.

- **Breaking Change: Support for double underlines when exporting to pdf and refactored TUIFont.** Now double underlines will be exported to pdf.  In order to support this we had to remove the **Underline** and **Strikeout** parameters from the [TUIFont](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TUIFont/index.html) definition, and put them in a separate [TUITextDecoration](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TUITextDecoration/index.html) structure.
So now the [DrawString](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Pdf/TPdfWriter/DrawString.html) methods in [ TPdfWriter](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Pdf/TPdfWriter/index.html) require a new TextDecoration parameter, and you don't specify the underline or strikeout anymore in TUIFont.

**This change can break some code if you are using TUIFont and DrawString directly**, but it should break at compile time and be straightforward to fix. Just create the TUIFonts without underline, and specify a text decoration when calling drawstring with those fonts. Take a look at the updated [Creating pdf files with pdf api](https://doc.tmssoftware.com/flexcel/vcl/samples/delphi/api/a0creating-pdf-files-with-pdf-api/index.html) demo to see how it works now.

- **New methods TUIFont.CreateFromMemory and TUIFont.CreateFromFile.** The new methods [TUIFont.CreateFromMemory](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TUIFont/CreateFromMemory.html) and [TUIFont.CreateFromFile](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TUIFont/CreateFromFile.html) allow you to create TUIFonts from fonts not installed in the system.

- **Improved conversion of control points in autoshapes between xls and xlsx files.** Now for some shapes like a roundrect or a smiley face are converted better to xlsx when read from xls files. The default control points for those shapes weren't converted correctly.

- **Now you can enter macros that refer to other files with the API.** Now when you call [AddButton](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/AddButton.html) or similar methods, you can use a macro that refers to a different file like file2!macro1. As usual APIMate will report the exact syntax to link to a different file.

- **Breaking Change: Added a new parameter to TExcelFile.RecalcRange.** Now when you call [RecalcRange](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/RecalcRange.html) you need to specify if the formula has relative references (as is the case in conditional formats, data validations and names) or if the references in the formula are absolute (as it is the case in normal spreadsheet formulas). Before this version RecalcRange assumed absolute references, so if you are updating existing code and want to keep the exact behavior just add ", false)" as last parameter. But make sure to review that the formula is not a relative formula.

- **Breaking Change: Bug Fix.** The parameters MaxWidth and MinWidth of the &lt;#column width> and &lt;#row height> tags weren't working properly when autofitting. Now they work according to the docs. If you were using MaxWidth and MinWidth in &lt;row height(autofit...)> or &lt;column width(autofit...)> please review those tags and make sure minwidth and maxwidth are in the correct positions.

- **FlexCel will now check names of tables are valid when you create a table with the API.** Now FlexCel won't let you name a table with an invalid name (like for example a name containing spaces).

- **Bug Fix.** When the print zoom was bigger than 100% the maximum column to print could be calculated wrong.

- **Bug Fix.** When evaluating data validations with  [CheckDataValidation](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/CheckDataValidation.html) introduced in FlexCel  6.15, INDIRECT functions using RC notation were evaluated wrong.

- **Bug Fix.** When doing bidirectional reports with multiple horizontal master detail X ranges, the rows for the vertical ranges could be wrong.

- **Bug Fix.** When a SPLIT tag was used inside a multiple master-detail relationship in a report the results could be wrong.

- **SKIA library updated to the latest.** We have updated the code that uses the SKIA library in Linux to the latest version of the library. We removed calls to deprecated methods and replaced them with equivalent methods.

- **Bug Fix.** When exporting arabic rich text with multiple formats in the same cell and a scale factor different from 1 to pdf the results could have the wrong font sizes.

- **Bug Fix.** Row() and Col() functions would return 1 when called from &lt;#Format range> or &lt;#Delete range> tags. Now they return the row and column of the cell where the tag is written.

- **Bug Fix.** Error when creating fonts in SKIA and Linux

- **Bug Fix.** Some non standard xlsx files could become invalid if you opened and saved them with FlexCel.



## New in v 6.15.0.0 - May 2017


- **Ability to check and evaluate data validations.** The new methods [CheckDataValidation](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/CheckDataValidation.html) , [CheckDataValidationsInSheet](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/CheckDataValidationsInSheet.html) and [CheckDataValidationsInWorkbook](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/CheckDataValidationsInWorkbook.html) allow you to check if the values of a cell, sheet or workbook are in conformance with the data validations in those cells. You can also check if a value would be valid when entered into a cell with [CheckDataValidation](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/CheckDataValidation.html)

- **Improved tagging of PDF Files.** Now repeated columns and rows are tagged as artifacts and not real content. This will also fix a rare bug that could happen when exporting a file with "Columns to Repeat at left" to tagged pdf.

- **Improved HTML5 exporting.** Updated the HTML5 exporting to comply with the latest HTML5 standard.

- **Improved bidirectional reports.** Now you can make a bidirectional report where the vertical range doesn't cross the horizontal range, but just is contained exactly in the top and bottom coordinates of the horizontal range.

- **Improved unicode Bidi Algorithm.** Updated the bid algorithm from version 3.0 to 6.3. Fixed errors that could happen when using invalid unicode characters.

- **Improved compatibility with invalid files.** Now FlexCel won't throw an exception by default when the file has invalid hyperlinks. You can change this behavior by setting the new "ErrorOnXlsxInvalidHyperlink" property in [ExcelFile.ErrorActions](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/ErrorActions.html)

- **Bug Fix.** FlexCel failed to open some encrypted Xlsx files saved in Excel 2013 or newer where the key size in the algorithm to encrypt the file was different from the key size in the algorithm to encrypt the key.

- **Bug Fix.** Reports in Delphi XE3 or older would raise an invalid typecast exception when referencing boolean types in records or classes. This was due to a bug in Delphi and didn't affect XE4 or newer.

- **Bug Fix.** When exporting to html a merged cell which had columns or rows not hidden but with zero width or height could render wrong.

- **Bug Fix.** When exporting files to PDF or images in iOS64 and you were using system colors (like clWindowsBackground) those colors would be wrong.

- **Bug Fix.** Now you can query if a page break at row 0 exists. A page break at row 0 would mean a page break before the first row, and Excel doesn't obey it, but you might end up with such a page break when deleting rows. Now you can check if there is a page break on that row.



## New in v 6.14.0.0 - April 2017


- **Support for RAD Studio 10.2 Tokyo including full Linux support.** FlexCel now fully supports Rad Studio 10.2, including support for rendering (exporting to pdf, images, html, svg, etc) in Linux using the SKIA graphics library.

- **New documentation center.** We've completely redesigned the documentation, including lots of new code examples, a tips and tricks section and much more. We've manually reviewed all the user guides to make sure they are up to date with the latest information. You can find the new documentation center at [our website](https://doc.tmssoftware.com/flexcel/vcl/index.html)
**Note**: This version removes support for integrating help in DelphiXE7 or older. For those versions you can't use F1 to get help and will have to manually search in the web or in the included chm file.

- **Support for Web Addins, either of Content or Task pane types.** Now FlexCel will preserve Web addins in xlsx files. There are 2 new methods in the API: `TExcelFile.HasWebAddinTaskPanes` and `TExcelFile.RemoveWebAddinTaskPanes` which you can use to know if there are any task pane addins in the file and remove them. The content addins are just objects and you can remove them with DeleteObject. You can find if an object is a Web Add-in by calling the new property `TObjectProperties.IsWebAddin`

- **Support for Table Slicers.** Now FlexCel will preserve Table Slicers in xlsx files (xls files don't support them). Note that Pivot Table Slicers where already preserved, this refers to the new Table Slicers in Excel 2013.

- **New static method `CreateKeepingAspectRatio` in `TClientAndhor` allows you to fit an image inside a range of cells maintaining the aspect ratio of the image.** You can either specify the 4 coordinates of the range where you want the image inside, and have the image centered or aligned inside that range, or you can leave one of the coordinates at -1. If you set Row2 or Col2 at -1, then this method will create an image that fits in the other Col1-Col2 or Row1-Row2 respectively, and keeps the aspect ratio.

- **New method SetTable allows to modify existing Tables.** While you could modify existing tables by using RemoveTable and AddTable, now you can modify them directly with SetTable.

- **New DrawBorders method in TExcelFile allows to quickly draw a border around a range of cells.** This new method is just a shortcut for calling [SetCellFormat](https://doc.tmssoftware.com/flexcel/vcl/api/FlexCel.Core/TExcelFile/SetCellFormat.html#texcelfilesetcellformatinteger-integer-integer-integer-tflxformat-tflxapplyformat-boolean) but it is a little easier to discover and use.

- **Now you can specify multiple folders with fonts when exporting to pdf.** Now in the OnGetFontFolder event of a FlexCelPdfExport you can return a list of strings separated by semicolons. So you can return a string like "c:\font1folder;c:\font2folder" and FlexCel will search for the fonts inside font1folder and font2folder.

- **Now &lt;#includes> in reports will balance in the containing band.** Now when you include a subreport in a report, the main parent will be balanced as it is with ranges inside ranges.

- **Bug fix.** TFlexCelPrintDocument.PrintAllVisibleSheets could print the wrong "page n of m" headers or footers when starting to print with a page not in the first sheet being printed.

- **Bug fix.** When you dropped a TFlexCelPreviewer in a FireMonkey form and run the app there would be an exception while debugging in Delphi Berlin about a non existing property. While the exception was caught and the app would run normally if you continued it, now no exception is thrown at all as we adapted the properties for Delphi Berlin.

- **Bug Fix.** When "Precision as displayed" was set to true in the file options, the recalculation engine could calculate some values with a different precision than the one in the cell.

- **Bug fix.** When a file with dates starting in 1900 had a linked formula to another file with dates stating in 1904 the value of the dates in the 1904 file would be considered to be at 1900. Similar for a 1900 file linking to a 1904.



## New in v 6.13.2.0 - February 2017


- **Support for drawing mirrored images when rendering.** Now when a bitmap is flipped vertically or horizontally, FlexCel will also draw it like this when exporting it.

- **New method TCellAddress.DecodeColumn.** This method is provided for symmetry with the existing TCellAddress.EncodeColumn, but it is normally not required as you can use TCellAddress to get the full cell address string for a row and a column. This method could be used in the rare case you only wanted the column string and not the full cell address.

- **Breaking Change: Support for losslessly rotated JPEG images.** Now when inserting JPEG images that are rotated via the "orientation" attribute in the JPEG file, FlexCel will automatically rotate the image so it appears with the desired orientation in Excel.
Before FlexCel behaved as Excel 2010 or older, just entering the image as is, so Excel would show it rotated. Now it works like Excel 2013 or newer, where we rotate the image in Excel to compensate. All orientation values are supported, included mirrors. Note that this change might be breaking if you were manually rotating the images before entering so they would show fine. If you ware rotating the images manually, you should remove the code as now it will be done automatically. There is also a new method `TImageUtils.GetJPEGOrientation` which you can use to tell if a JPEG image is rotated or not.

- **Bug Fix.** Support for reading xlsx files with custom properties with repeated names or empty names.



## New in v 6.13.1.0 - January 2017


- **New method TXlsFile.AddAutoShape to add autoshapes with the API.** The new method allows you to add an autoshape to a file. As usual APIMate will provide you with the needed code.

- **Bug Fix.** The TFlexCelPreviewer component would raise an Exception when trying to display a file.

- **Bug Fix.** When autofitting a column which contained multiple lines but the cell was set to not wrap, FlexCel would consider that the cell could wrap and so end up with a smaller column width than needed.

- **Bug Fix.** Xml declarations when writing custom xml parts could be duplicated.



## New in v 6.13.0.0 - January 2017


- **Support for rendering Right-To-Left sheets.** Now FlexCel can export sheets where A1 is at the right side of the page and the cells grow to the left instead of to the right. A new property `XlsFile.SheetIsRightToLeft` allows you to read or write the right to left state of the sheet directly without needing to use SheetOptions. APIMate will now also suggest SheetIsRightToLeft instead of SheetOptions for RTL sheets.

- **Improved right to left support for text.** Now FlexCel will support mixed right to left and left to right text more as the Unicode BIDI algorithm defines it. The **Context** property of the cell is now also used to figure out if it is rtl text embedded in ltr text or ltr text embedded in rtl text.

- **New static properties `TExcelFile.CompressionLevel`,  `TFlexCelConfig.XlsxCompressionLevel` and `TFlexCelConfig.PdfPngCompressionLevel`.** Properties `TExcelFile.CompressionLevel` and `TFlexCelConfig.XlsxCompressionLevel` are the same and control the zip compression level used to creating xlsx files. `TFlexCelConfig.PdfPngCompressionLevel` controls the compression level for pdf and png files. FlexCel uses "zcDefault" zlib compression level, which normally gives the best ratio between speed and size. But note that Excel itself uses zcFastest when saving xlsx files, resulting in faster saves but also bigger files. While you won't probably want to change the defaults, now you can. 

- **New static property FlexCelConfig.DpiForReadingImages.** This new property `FlexCelConfig.DpiForReadingImages` allows you to force a resolution in the images you are loading. Normally FlexCel will use the resolution stored in the images to calculate the desired width in inches, but now you can override whatever is saved in the file by changing this property.

- **New implementation of wildcard matching for all functions that use them.** The new algorithm to match patterns like * or ? and used in functions like MATCH or COUNTIF is now much faster and can use much less memory in pathological cases.

- **New method `FlexCelReport.Run(Stream templateStream, Stream outStream, TFileFormats fileFormat)`.** This method allows you to specify the resulting file format when running a report to a stream.

- **Better handling of expressions or formats defined both in an included report and the master report.** Now when an included report has the same expressions or formats defined in the config sheet as the master, those local definitions will be used, instead of raising an error of repeated formats/expressions.

- **Breaking Change: Better handling of image resolution in reports.** Now when adding an image to a report and resizing it, FlexCel will take in account the image resolution if it is saved in the image. If the image doesn't have a resolution saved, FlexCel will use the screen resolution.
You can revert to the old way of assuming a resolution of 96 dpi for all images by changing FlexCelConfig.DpiForReadingImages

- **Bug Fix.** When exporting to HTML and a merged cell covered hidden rows or columns, the resulting html could be wrong.

- **Bug Fix.** When exporting to HTML with embedded SVG images, the fill colors in the SVG images would be wrong if there were gradients.

- **Bug Fix.** When exporting to SVG, text in controls or shapes could go a little lower than it should.

- **Bug Fix.** The formula parser would fail to detect some unicode characters as valid characters for a sheet name or named range.

- **Better display of complex numeric formats.** Now we handle some complex formatting the same as Excel does, handling also invalid formats which Excel doesn't allow better.

- **Bug Fix.** Now FlexCel allows names with spaces as macro identifiers when loading files. While those aren't valid names and Excel won't let you enter them directly, you can enter them with VBA code, and FlexCel was refusing to read those files. Now FlexCel will open them correctly.

- **Bug Fix.** When a file had "Precision as displayed" set and there were cell formats including percentage signs, the numbers might be rounded wrong.

- **Bug Fix.** Report filters in the config sheet could have wrong results for some values.

- **Bug Fix.** When using a report as a master in a sheet name, and the detail was the same dataset filtered, FlexCel would raise a range check error.

- **Bug Fix.** There could be an stack overflow when a camera object rendered a range of cells which included the cells where the camera object was.



## New in v 6.12.0.0 - October 2016


- **Improved performance when creating tens of thousands of names in a file.** Now when creating a file with tens of thousands of names FlexCel will be much faster.

- **Breaking Change: Bug Fix.** In xls files, setting SheetProtection.Scenarios and SheetProtection.Objects had the reverse effect as in xlsx files. Now xls files behave the same as xlsx files. If you are changing the protection of  xls files, **review the calls to `SheetProtectionOptions.Objects` and `SheetProtectionOptions.Scenarios` as they might be reversed.** If you are saving as xlsx files, then there is no need to change anything, as xlsx already worked as expected.

- **Better drawing of labels in charts.** Now the labels inside charts draw more like Excel when exporting xls files to pdf or html. If multiple labels would overlap, now FlexCel tries to separate them. The leader lines in pie charts from the slices to the legends render better too.

- **APIMate will now suggest to use TSheetProtection.Create(TProtectionType.All/None) instead of  TSheetProtection.Create(true/false).** The constructors using true and false can be confusing, because while they work, they will set all the protection to true and false, and some protections work when the property is true (contents, objects and scenarios) while the others work when the property is false (all the other properties). The constructors using TProtectionType will set some values to true and some to false as needed to have all the sheet protected or unprotected.

- **Bug Fix.** When copying sheets in a file, some conditional formats could raise a null reference exception.

- **Improved compatibility with third-party created files.** Specifically, we now can read spreadsheets created with google docs which contain pivot tables. Those generate invalid xlsx files lacking required attributes, and FlexCel would complain about them missing. Now it will ignore them, and fix the files if you open and save them in FlexCel.

- **Bug Fix.** The &lt;#delete range> tag in reports might not work in some cases.



## New in v 6.11.0.0 - September 2016


- **Support for Excel tables in xlsx files.** There is partial support for tables in the FlexCel API.
   * Tables are preserved when editing xlsx files. Note that we refer to the tables introduced in Excel 2007: Other tables like "what-if" tables were already preserved.
   * Tables will be copied and modified when you insert or copy ranges.
   * API for reading tables
   * Preview API for writing tables. **Note that this API is not complete yet and might fail in some cases**. APIMate will show you how to add a table with the API.
   * There is no rendering yet (exporting tables to pdf, etc), and no calculation of table references like =SUM(@Table1[column2]

- **Support for Delphi Starter.** New binary setup added to install in Delphi Starter.

- **New properties `FullRecalcOnLoad` and `FullRecalcOnLoadMode` in TXlsFile.** `FullRecalcOnLoad` will tell you if the xlsx file opened with FlexCel had the property "Full Recalc on Load" true. When it is true, normally the file doesn't have the values of the calculated formulas and you need to do a manual XlsFile.Recalc() to get the values. `FullRecalcOnLoadMode` allows you to tell FlexCel how it should mark the files it creates. In the default mode it will mark them as not needing full calculation id they were calculated on save by FlexCel (the default) and mark them as needing recalc on open in other case. Note that those 2 properties only apply to xlsx files: xls files don't have this property and the value returned by those properties will always be false.

- **Some repeated function results are now calculated only once for better recalculation speed.** Now FlexCel can detect repeated subexpressions inside a formula and calculate them only once. So for example if you have a thousand formulas like `=If(A1,2,3... = Sum($B$1:$E$1000),1,Sum($B$1:$E$1000))` then the Sum($B$1:$E$1000) will be calculated only once for all the formulas. This can have significant speed improvements if you have formulas with this pattern.

- **Performance improvements in function calculations.** Some of the most used functions like SUM, COUNT, AVERAGE, SUMIF, COUNTIF, etc have been optimized to work at a higher speed.

- **Performance improvements in formula parsing.** Now the formula parser is a little faster and that can lead to faster loading of xlsx files with thousands of formulas.

- **Performance improvements loading xlsx files with thousands of comments.** Now xlsx files with thousands of comments should load much faster.

- **Improved rendering of numbers which don't fit inside a cell.** When a number doesn't fit inside a cell, Excel shows #### instead. But it will always show at least one #, if it can't fit a complete # into the cell, then it will display it empty. FlexCel was showing part of a # sign when a full # sign wouldn't fit, not it behaves as Excel and shows the cell empty.

- **Bug Fix.** In form objects like checkboxes or listboxes saved by Excel 2007 in xlsx files, the resulting coordinates could be wrong if the value of the anchor took more than one cell. FlexCel would move the anchor to the next cell, but Excel just ignores the extra width or height. Note that this only applies to xlsx files saved by Excel 2007, xls files or xlsx files saved by Excel 2010 or later would be correctly read by FlexCel.

- **Bug Fix.** When deleting sheets with locally stored defined names and you had multiple references to those names in a single formula, FlexCel could fail to update the names.

- **Bug Fix.** When setting a column format for many columns at the same time and reset cells true, some cells might not be reset.

- **Bug Fix.** Now FlexCel won't let you enter formulas with unions ranges of numeric or string values. Before it would allow you to enter a formula like "=1, 2" and it would be interpreted as the union of the reference "1" and "2". Excel would read it if saved as xls, but would fail to parse the formula when saved as xlsx. So now we don't allow those formulas anymore.

- **Bug Fix.** While it is invalid to write a file with conditional formats or data validations with formulas that refer to other sheets, Excel can load them (but you won't be able to modify them). Now FlexCel can read those too without reporting an error.

- **Bug Fix.** FlexCel could raise an exception when deleting ranges with conditional formats.



## New in v 6.10.0.0 - August 2016


- **Support for converting conditional formats between xls and xlsx files.** Together with the support for conditional formats in xlsx files introduced in 6.9, this completes full support for conditional formats in xls or xlsx files. Now the APIs to read and write conditional formats will work in both xls and xlsx, and conditional formats will convert seamlessly between xls and xlsx files, even formats not supported in the original xls97 spec.

- **Perfomance improvements in pdf engine.** The pdf engine is now up to 2 times faster when writing files to disk. We made a lot of optimizations to the rendering engine to make it possible.

- **Support for using formulas in "Text" conditional formats.** Formulas weren't allowed in Excel 2007, and FlexCel 6.9 didn't allowed them either. Now they are fully supported, for Excel 2010 and newer.

- **Fixed small validation issues in the xml generated for xlsx files.** Some xlsx files generated by FlexCel could have xml that would not validate against the xlsx reference files. Excel would still open those files, but the spec wasn't correctly implemented.

- **Breaking Change: Removed "IsPercent" property from Iconset Conditional Format definitions.** IsPercent had no effect in IconSet rules and it is deprecated in Excel. As IsPercent was introduced in  the previous version 6.9, it made sense to remove it before it got into wide use.

- **Bug Fix.** Sometimes with very complex groups of conditional format rules, some could be ignored when exporting to pdf.

- **Bug Fix.** Reversed iconsets were exported not reversed to pdf.

- **Bug Fix.** When copying cells with conditional formats from one xlsx file to another, the borders wouldn't be copied.

- **Bug Fix.** C++ builder XE7 or older would raise a linker exception when compiling an app using FlexCel without packages in 32 bit.



## New in v 6.9.0.0 - August 2016


- **Conditional Format support for xlsx files.** We've added support for conditional format in xlsx files:
  * All xlsx conditional formats including the new ones added to xlsx in Excel 2010 are fully parsed and preserved. When you insert and copy ranges, conditional formats will adapt and be copied too.
  * Full support to read and write them with the API. APIMate also fully supports them and will show you the code you need to enter a conditional format into a file.
  * Full support for exporting all conditional formats to pdf or html. All formats are exported to pdf. When exporting to html, iconsets and databars are not exported, but they aren't exported either when you save as html in Excel. Different from Excel, we export the iconsets to pdf as vectors, so they will look nice in any zoom level.

- **Perfomance improvements in exporting.** Exporting files to pdf or images is now faster. Depending in your files, you might see a visible improvement.

- **Performance improvements in CSV exporting.** CSV exporting is now up to 2 times faster.

- **Improved C++ builder compatibility.** SetCellValue methods had a default value for XF parameter in TExcelFile, but that wasn't repeated in the inherited class TXlsFile. In Delphi it works fine, but in C++ Builder this would mean that you could use the default value for TExcelFile objects, but not for TXlsFile objects (even if TXlsFile is a TExcelFile descendant).

- **Font could be wrong in linked shapes.** When you had a shape whose text was linked to a cell and the value of the cell changed, the font of the shape text would be reset.



## New in v 6.8.8.0 - August 2016


- **Bug Fix.** When rendering superscripts in multiline cells, the distance between lines could be wrong.



## New in v 6.8.7.0 - July 2016


- **Unknown root parts preserved in xlsx/m files.** Now root parts which do not conform to the xlsx spec like ribbon customization or arbitrary parts are preserved when editing xlsx/m files.



## New in v 6.8.6.0 - July 2016


- **User Customization parts preserved in xlsx/m files.** Now the buttons that you add to the *Quick access toolbar* in the ribbon for only a specific document will be preserved when you edit the document with FlexCel.

- **Bug fix.** Some invalid png files could cause exporting to pdf to hang.

- **Bug fix.** A chart with an empty array as range would throw an Exception when saving in xlsx files.



## New in v 6.8.5.0 - June 2016


- **Controls and drawings in xlsx now are stored in the same hierarchy and a control can be below a shape.** The xlsx file format introduced in Excel 2007 had controls and drawings in separate parts, so all controls were always above any drawing, and also it wasn't possible to group controls and images. Since Excel 2010 shapes and controls are also stored in a  common stream so you can group them or put images above controls. Now FlexCel reads and writes the Excel 2010 parts if available, and correctly puts the controls below the images or grouped if needed. Note that this applies only to xlsx, it was always possible to group controls and images in xls.

- **Bug fix.** Grouped shapes with more than 2,147,483,647 emus height (approximately 38,000 rows with standard row heights) would be truncated in xlsx files (xls files are always truncated anyway since that is a limitation of the file format).

- **Bug fix.** External links could fail to load in xlsx files in Excel 2007. (Excel 2010 and up were already ok)



## New in v 6.8.4.0 - June 2016


- **New TXlsFile.RenderCells overload which allows to render objects and borders.** Now RenderCells can render also the objects which are in the group of cells.

- **Support for rendering linked images (camera tool) to pdf/html/etc.** Now FlexCel will update the linked images when rendering to show the correct image.



## New in v 6.8.2.0 - June 2016


- **Support for preserving ActiveX controls in xlsx files.** Now FlexCel will preserve ActiveX controls when you open, modify and save xlsx/m files. ActiveX objects are not converted between xls and xlsx files.

- **Form controls are now read from and written to the Excel 2010 stream besides the Excel 2007 stream.** FlexCel now reads the Excel 2010 stream for Form controls and uses it if available instead of the Excel 2007 stream. It also now writes both an Excel 2007 and 2010 stream. The Excel 2010 stream is better because it saves the coordinates in device independent units, so controls will look fine when opened in High DPI displays. Excel 2007 on the other hand uses real pixels, which results in different dimensions for the controls when opened in high dpi mode.

- **Files created with NewFile will now not have printer settings, and the locale of them all will be English.** Depending in the Excel version passed to NewFile, FlexCel could add some printer settings to the empty file, and some versions had different locales. Now all locales for files created by NewFile are US English, and there are never printer settings.

- **Support for camera tool (linked images) in xlsx files.** Now "camera tool" pictures will be preserved when saving to xlsx, and converted between xls and xlsx. They will also update when you insert rows or columns. Note that FlexCel won't update camera tool images if the cells change, but they will be updated by Excel when you open the file.

- **New global variables TSmoothingMode_FlexCelDefault and TInterpolationMode_FlexCelDefault.** Those new variables let you decide what is the default antialiasing and interpolation mode used when rendering images.

- **Breaking Change: Autoshapes in xls files are now rendered using the xlsx definition of them if it is stored in the file.** Excel 2007 and newer save the autoshapes in two different places inside an **xls** (not xlsx) file: One that is read by Excel 2003 or older, and the other which is read by Excel 2007 or newer. FlexCel used to read the section of Excel 2003 or older to render the autoshapes, now it is using the section of Excel 2007 or newer.
While in general this should improve autoshape rendering, note that this change is potentially breaking if you have files with the correct definition in the xls section and incorrect in the xlsx section. For more information, please see: [https://tmssoftware.com/site/blog.asp?post=347](https://tmssoftware.com/site/blog.asp?post=347)

- **Recovery mode can now open files with invalid format strings.** Now when XlsFile.RecoveryMode = true and the file has invalid format strings, FlexCel will open the file anyway and report the errors in FlexCelTrace.

- **Bug Fix.** FlexCel could fail to load some CSV files.

- **Bug Fix.** In some border cases when opening and saving a file multiple times and adding the same format every time, the format could be added each time instead of detecting it already existed.

- **Bug Fix.** Localized projects could fail to find FlexCel resources.

- **Bug Fix.** Some autoshapes with holes inside could be rendered as fully filled.

- **Bug Fix.** Improved rendering of custom xls autoshapes

- **Bug Fix.** There could be an error when saving pivot cache slicers or timelines in multiple sheets.

- **Bug Fix.** Some colors in controls or shapes in xls files could be read wrong.

- **Bug Fix.** Improved compatibility when opening invalid xlsx files.



## New in v 6.8.1.0 - May 2016


- **Bug Fix.** When pasting as text an empty row like $D$A into FlexCel, it would raise an exception.



## New in v 6.8.0.0 - April 2016


- **Support for Rad Studio 10.1 Berlin.** FlexCel now supports Rad Studio 10.1 Berlin

- **Full support of Hyperlinks in autoshapes in xlsx files.** Now hyperlinks in shapes inside xlsx files are fully preserved as they were in xls files. They also will convert between xls and xlsx, and you can change the hyperlinks of the shapes with xls.SetObjectProperty. Links are exported to pdf, html and svg.

- **Full support for "Allow users to Edit ranges" in the API.** The new methods `XlsFile.Protection.AddProtectedRange`, `XlsFile.Protection.DeleteProtectedRange`, `XlsFile.Protection.ProtectedRangeCount` and `XlsFile.Protection.ClearProtectedRanges` allow you to read and modify protected ranges. Note that for simple protection you can still just lock or unlock the cells in the cell formatting. APIMate should report now how to enter Protected Ranges too.

- **New &lt;#Switch> and &lt;#IFS> tags in FlexCel reports.** Those tags behave like the  [IFS](https://support.office.com/en-us/article/IFS-function-36329a26-37b2-467c-972b-4a39bd951d45?ui=en-US&rs=en-US&ad=US) and [SWITCH](https://support.office.com/en-us/article/SWITCH-function-47ab33c0-28ce-4530-8a45-d532ec4aa25e?ui=en-US&rs=en-US&ad=US) functions added in Excel 2016 january update. They can eliminate "if chains" and make the expressions simpler. For example `&lt;#ifs(&lt;#value> &lt; 10;&lt;#format cell(red)>;&lt;#value> &lt; 20;&lt;#format cell(yellow)>;true;&lt;#format cell(green)>)>`

- **Autosize of chart axis when rendering charts.** Now when exporting xls charts to pdf/html/etc, the axis of the chart will move to fit the data in the axis so it doesn't get cut out.

- **New parameter `convertFormulasToValues` added to PasteFromXlsClipboardFormat.** This parameter will allow you to paste the formulas as values from the clipboard. This is useful specially if the formulas you are pasting reference other books, so they won't reference the correct cells when pasted.

- **New parameter `recalcBeforeConverting` added to ConvertFormulasToValues and ConvertExternalNamesToRefErrors.** This parameter will allow you to convert formulas to values without first having FlexCel recalculating the file (which was the default before). So if your file can't be recalculated by FlexCel because for example it contains links to other files that don't exist anymore, you can still convert the formulas to the latest calculated values.

- **New overload of TFlexCelPdfExport.ExportAllVisibleSheets taking a filename.** This overload is a shortcut for creating a filestream, calling BeginExport on the stream, then calling ExportAllVisibleSheets and then calling EndExport.

- **Better performance when opening csv files.** The speed in opening CSV files can be up to 10 times faster now.

- **Support for ShrinkToFit attribute in cells when exporting to pdf/html/svg/images/printing/previewing.** Now the ShrinkToFit attribute of cells is rendered when exporting, and will show in printing, previewing and exporting.

- **Support for adding horizontal scrollbars with the API.** There is a new property in TSpinProperties which allows to specify if the scrollbar is horizontal. APIMate will report how to do it from a horizontal scrollbar in Excel.

- **&lt;#IF> tag in reports can now omit the false section.** You can now write a tag like &lt;#if(true;hi)> instead of &lt;#if(true;hi;)>

- **Better chart rendering for xls files.** Now the labels overflow in a way similar to Excel, and FlexCel calculates the chart axis positions so t won't overflow.

- **Performance tweaks on the codebase.** We changed the hash algorithm used by FlexCel from Lookup3 to Mumur3, added direct overloaded functions to enter strings and numbers into cells, and many other small tweaks that should make FlexCel a little faster overall.

- **The file created by TXlsFile.NewFile(n, TExcelFileFormat.v2016) now is in the Excel "January update" format.** The "January update" of Excel 2016 added some new fonts to the themes and changed the build id of a default empty file. Now the empty files that FlexCel generates when you specify v2016 include those new fonts in the themes. The build id had already been updated in a previous FlexCel release.

- **Bug Fix.** When exporting xls bar and column charts with a single data series and  "Vary colors per point" = true, FlexCel was not changing the colors on each point.

- **Bug Fix.** When copying sheets with data validations to other files, and the data validations would refer to a list in a different sheet, the data validation would be copied wrong.

- **Bug Fix.** When rendering conditional formats in xls files sometimes the background color could be ignored.

- **Bug Fix.** When importing fixed text with blank lines, the file might not be imported on its totality.

- **Bug Fix.** The constructor of TBlipFill wasn't public.

- **Bug Fix.** TXlsFile.DpiForImages would be ignored in some metafiles.



## New in v 6.7.16.0 - March 2016


- **Support for the new functions introduced in the Excel 2016 January Update.** Now FlexCel can recalculate and recognize the 6 new functions introduced in the [Excel 2016 January Update](https://support.office.com/en-us/article/What-s-new-in-Excel-2016-for-Windows-5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73?ui=en-US&rs=en-US&ad=US) : [TEXTJOIN](https://support.office.com/en-us/article/TEXTJOIN-function-357b449a-ec91-49d0-80c3-0e8fc845691c?ui=en-US&rs=en-US&ad=US), [CONCAT](https://support.office.com/en-us/article/CONCAT-function-9b1a9a3f-94ff-41af-9736-694cbd6b4ca2?ui=en-US&rs=en-US&ad=US), [IFS](https://support.office.com/en-us/article/IFS-function-36329a26-37b2-467c-972b-4a39bd951d45?ui=en-US&rs=en-US&ad=US), [SWITCH](https://support.office.com/en-us/article/SWITCH-function-47ab33c0-28ce-4530-8a45-d532ec4aa25e?ui=en-US&rs=en-US&ad=US), [MINIFS](https://support.office.com/en-us/article/MINIFS-function-6ca1ddaa-079b-4e74-80cc-72eef32e6599?ui=en-US&rs=en-US&ad=US), [MAXIFS](https://support.office.com/en-us/article/MAXIFS-function-dfd611e6-da2c-488a-919b-9b6376b28883?ui=en-US&rs=en-US&ad=US).

- **Updated the RecalcVersion for Excel 2016 to the Excel 2016 January Update.** The january update of Excel 2016 changed the RecalcVersion id saved in the xls and xlsx files. This means that xls or xlsx files saved with Excel 2016 "pre-january-update" would ask for saving when opened and closed in Excel 2016 "post january update". Now when you choose the RecalcVersion in FlexCel to be 2016, FlexCel will identify the file as saved by "post-january-update" Excel 2016. This will avoid the save dialog when opening in Excel 2016 with all the updates.

- **New value in TRecalcVersion:  "TRecalcVersion.LatestKnownExcelVersion" will identify the file saved by FlexCel as the latest Excel version that FlexCel knows about.** If you set xls.RecalcVersion to be TXlsRecalcVersion.LatestKnownExcelVersion then FlexCel will identify the file as saved by the latest Excel version it is aware of. Currently this means the files will be identified as saved by Excel 2016 january update. When newer Excel versions appear and FlexCel is updated to support them, then this version will automatically increase to the latest without needing to modify your source code.

- **New property UsedZoom in TOneImgExportInfo.** The property `UsedZoom` will tell you the actual zoom that is going to be used when printing or exporting the sheet. So you now can call `TFlexCelImgExport.GetFirstPageExportInfo` and get the zoom of the pages that will be printed, including the zoom calculated for print to fit if set.

- **Improved compatibility with invalid xls and xlsx files.** Now FlexCel will fix files which have an invalid active sheet stored, and set the active sheet to the first in those cases.

- **Improved compatibility with thid party xlsx files.** FlexCel will now understand xlsx files which use absolute references like $A$3 in cell value addresses. Note that Excel never writes absolute references in the cell values addresses, but some third parties might. Now you will be able to read those files too.

- **Bug Fix.** When exporting sheets with multiple print ranges, and those print ranges had different zoom (due to having a PrintToFit zoom), FlexCel could raise an error. Now, similar to Excel, it will calculate the smallest zoom needed for all the ranges, and use that in all the print ranges.

- **Bug Fix.** Formatted tags inside autoshapes would lose their format when replaced in a report.

- **Bug Fix.** Rendering of images in headers and footers in xlsx files could be wrong if the sizes in the file were in mm.

- **Bug Fix.** A report without any tags in cells, but with tags inside shapes would not replaces those tags.

- **Bug Fix.** Empty Default values in tags inside reports weren't working. So if you wrote "&lt;#Db.SomeFieldThatDoesn'tExist;>" in a template, then an exception would be raised to tell the field didn't exist. Now it will correctly set the value to empty since it has a semicolon (;) meaning an empty default value at the end of the tag.

- **Now TReportValue converts automatically from an Extended floating point type.** Now you can write something like Report.SetValue(10.2) without converting the extended 10.2 into a double first.



## New in v 6.7.12.0 - February 2016


- **New properties TExcelFile.HeadingRowHeight and TExcelFile.HeadingColWidth.** Those properties allow you to specify the width of the heading column and the height of the heading row when printing headings or exporting them to pdf via FlexCel. The "Custom preview" demo now sets those properties so the sizes are automatic.



## New in v 6.7.11.0


- **BugFix.** Times or dates shown in the headers and footers when exporting to pdf or html could have the wrong format.



## New in v 6.7.10.0 - February 2016


- **BugFix.** When using TFlexCelImgExport.ExportNext to save to a file without transparency (like JPEG), the background would be black. Now it should be transparent if the format supports Alpha channels, and white otherwise.



## New in v 6.7.9.0 - February 2016


- **New static events TUIFont.FontCreating and TUIFont.FontCreated.** Those events allow you to customize the font replacements in your system. For example, if you have Excel  files that have a font "MyDeprecatedFont" and you would want to replace it by "MyNewCoolFont" when exporting to pdf, you can use the FontCreatingEvent to do so. You can use the FontCreated event to catch fonts where the original wasn't present in the machine and were substituted by the operating system into something else. You can then provide a different substitute font.



## New in v 6.7.8.0 - February 2016


- **New methods OffsetRelativeFormula and RecalcRelativeFormula in TExcelFile.** Those new methods allow you to know the real value of a **relative formula**, such as those returned by **names** and **data validations**. Relative formulas depend on the cell the cursor is, so if the cursor moves the formula changes. As FlexCel doesn't have a cursor, it always returns the formulas considering the cursor at A1. With OffsetRelativeFormula you can get how the formula would look like when the cursor is at for example B3, and with RecalcRelativeFormula you can recalculate the formula and get the result when the cursor is at B3.

- **Support for quoted column names in reports.** Now you can quote a column name inside a tag in a report, like &lt;#"db.column ) "> This can be useful if you have column names with for example unbalanced parenthesis. Note that you don't need to quote the name if it has balanced parenthesis.

- **Bug Fix.** In some cases when opening an xls file with existing formats, and calling AddFormat for a format already present in the file, FlexCel would fail to realize the format already existed and create a new one. This could lead to having more formats than the number allowed by Excel if you opened a file, added existing formats and save it a lot of times.

- **Bug Fix.** When &lt;#including> subreports inside FlexCel Reports with the RC option, empty row formats would be copied to non empty row formats.

- **Bug Fix.** ActiveX controls with a size larger than an Int32 would raise an Exception when loading.

- **Bug Fix.** Bidirectional reports could fill some wrong cells when using multiple master-details in the rows.

- **Bug Fix.** Xlsx files with autofilters could become invalid if you deleted the range which contained the autofilter.

- **Bug Fix.** VLookup and HLookup would return a match if you searched for a blank string ("") and the cell was empty. Excel doesn't return a match in those cases, and now FlexCel doesn't either.

- **Bug Fix.** Double bordered lines could render wrong when the zoom was big (about 200% or more)

- **Bug Fix.** Some invalid formulas including more than one "=" sign in a not valid location, like `"=1 + =1"` didn't throw an Exception when you tried to manually enter them, and would raise the exception later when trying to save. Now FlexCel will report those formulas as invalid when you try to enter them.

- **Bug Fix.** Components in the palette would show only as Win32compatible for Delphi XE6 or newer, even if they were compatible with all platforms. Now they show correctly

- **Bug Fix.** DISTINCT tag in Reports could fail in Delphi 64 bits.



## New in v 6.7.3.0 - January 2016


- **New JOIN and UNION commands for reports.** Those commands are written in the config sheet and allow you to either *JOIN* the columns of multiple tables into a single table, or to do an *UNION* of the rows of multiple tables into a single one. See the new "Join and Union" demo.

- **Improved bidirectional reports.** Now bidirectional reports can work with rows in master detail and they also will delete empty column bands if none of the columns has records.

- **Improved preservation of timelines in xlsx.** Timelines are a feature introduced in Excel 2013, which allow you to graphically navigate a timeline in a data source. Now FlexCel should preserve timelines for pivot tables.

- **ReportConverter will now convert mutliple ranges in v3 to JOIN tables in v6.** Now when converting FlexCel 3 reports, the converter will convert names like __dataset1__dataset2__dataset3__ into a JOIN(dataset1; dataset2; dataset3)

- **Bug Fix.** Fixed order of records specific for Excel 2010 to workaround a bug in Excel 2010. Some very complex files could raise an error when opened in Excel 2010, even when they were correct by the xlsx spec.



## New in v 6.7.2.0 - December 2015


- **Copy to the clipboard now supports html.** Now there is an extra option in the formats to be copied to the clipboard: In addition to native xls (best for copying from one spreadsheet to another) and text (for apps that don't understand anything else), now you can also copy as html, which gives the best results when pasting a spreadsheet in Microsoft Word or PowerPoint. You can copy to html either using XlsFile.CopyToClipboardFormat or FlexCelHtmlExport.ExportToClipboardFormat.

- **Bidirectional Reports.** Now you can create ranges in shape of a cross that expand to the right and down at the same time. While you could do this before by splitting one of the ranges in 3, now you can directly intersect the ranges and get the correct result. Take a look at the new Bidirectional Reports demo and the documentation in the report designer guide.

- **Breaking Change: FlexCelFormatSettings methods now need a "Locale String" as a parameter.** This locale string is used to know the sort order of the locale, to allow correct sorting. Now calls to methods like `TFlexCelFormatSettings.SetGlobalFormat(fmt)` will be like  `TFlexCelFormatSettings.SetGlobalFormat('en-US', fmt)`

- **Changed default fallback fonts in pdf.** Windows 10 doesn't come with MS Mincho or MS Gothic installed by default (you need to manually install the language packs to get the fonts). So now FlexCel looks for both MS Mincho/Gothic (for windows older than 10), and YuMincho/Gothic for Windows 10.

- **The tags &lt;#List>, &lt;#DbValue> and &lt;#Aggregate> can now work inside nested Array/Linq datasets.** Now when you have a master detail relationship where the detail is a property of the master, FlexCel can find the master dataset for the &lt;#List>, &lt;#DbValue> and &lt;#Aggregate> even when they are not added with AddTable.

- **New property XlsFile.DocumentProperties.PreserveModifiedDate.** FlexCel by default sets the modified date of the files it saves to the date when the file was saved. But if you want to change this date to an arbitrary date, then you can set PreserveModifiedDate to true.

- **FlexCel will now set the creation and modification date in xls files too.** Now Creation and Modification dates are stored in xls files, same as they already were in xlsx.

- **FlexCel will now allow you to set the file creator for xlsx files.** By default, files created by FlexCel are identified as created by FlexCel in the document properties. Now you can change the application creator by writing ``xls.DocumentProperties.SetStandardProperty(TPropertyId.NameOfCreatingApplication, "SomeNewCreator")``

- **Bug fix.** LastModifiedDateTime wasn't returned correctly for xlsx files.

- **Bug fix.** FlexCelPreview could get too slow if you had thousands of merged cells.

- **Bug fix.** Macros converted from xls files to xlsx could fail to open in Excel 2016 in some border cases.

- **Bug fix.** Nested &lt;#aggregate> or &lt;#list> tags could fail for reports using TDataSet as datasources.

- **Improved support for C++ builder FMX.** Now FlexCel should work better in FMX C++ cross platform applications.

- **Improved setup.** Now you can opt to not compile Debug dcus when installing FlexCel. This will disable the possibility to debug FlexCel code, but it will install twice as fast and use half the disk space.

- **Improved Getting Started document.** Now GettingStarted shows actual code examples on how to do simple tasks and contains links to all documentation.



## New in v 6.7.1.0 - November 2015


- **Support for new Excel 2016 features.** While old FlexCel versions will still work fine with Excel 2016 (as expected), FlexCel now provides support for new extra features in Excel 2016. Now XlsFile.NewFile allows to create files like Excel 2016 creates by default. Also XlsFile.RecalcVersion has a 2016 option to tag your files as created by Excel 2016 so Excel 2016 doesn't ask for saving when closing them.

- **Improved  installation speed.** We have refactored the code to make it easier for the Delphi compiler to compile it. This lead to about 10 times faster compile times, which mean the setup will install FlexCel in about 1/10 of the time it used before.

- **Improved support for DataValidations that have lists with cells from other sheets.** DataValidations with lists of cells from other lists were introduced in Excel 2010, and while FlexCel preserved them, it wouldn't modify them when inserting or deleting ranges. They wouldn't either be reported by the API. Now they are modified and also reported by the API, just like all the other data validations.

- **Slicers for Pivot Tables are now preserved in xlsx.** Now FlexCel will preserve the slicers for pivot tables present in xlsx files. This is a feature available only in Excel 2010 or newer, so you won't see them in older Excel versions, but the generated files will still open without errors.

- **Excel 2010 equations are now preserved in xlsx.** Now FlexCel will preserve the new equations in Excel 2010 (Ribbon->Insert->Equation)

- **Center across selection cells are now exported to html.** Now html export will export cells marked as "center across selection", same as exporting to pdf or other exports already did.

- **Improved exporting of superscripts and subscripts to html.** Now superscripts and subscripts are exported better to html files.

- **Full support for formulas attached to textboxes or autoshapes.** Now FlexCel will preserve and convert betwen xls and xlsx textboxes or shapes which have their text linked to a formula. If you modify the linked cell, the text in the textbox will change.

- **New methods XlsFile.SheetID and XlsFile.GetSheetIndexFromID.** Those new methods can be used to identify a sheet in a FlexCel session and get it back later. Note that as this ID is not saved in the file, it will change every time you load a new file and so it can only be used in a single session.

- **Data validations entered manually in xls files could fail to work when opened in Excel.** In some border cases, Excel would report all values as invalid for a data validation entered with FlexCel, even if the values were valid. This only applied to xls files.

- **Now FlexCel can open xlsx files with images with the wrong image type.** If an xlsx file now contains for example a png but it is declared as jpg, now FlexCel will open it as a png anyway. This will only happen with corrupt files or files generated by incorrect third-party products.

- **Improved =RoundUp and =RoundDown compatibility with Excel.** Now when a number is just a delta over the integer part (like in 345.00000000000006) it will not be rounded up to the next integer (346) but to the nearest (345). Excel works this way, so RoundUp/Down in FlexCel could be returning different (if correct) results for those border cases.

- **Error when deleting rows in a pivot table.** When deleting rows in a pivot table in an xlsx file, the rows could go negative creating invalid files.

- **Bug Fix.** FlexCel could fail to load the recalculated value of formulas whose result was an empty string in xlsx files.

- **Bug Fix.** Reports could fail with some combination of format row tags

- **Bug Fix.** Xlsx files with 0 bytes xml files inside could throw an "Invalid XML file" error.

- **Improved compatibility with third-party tools.** Workaround for some tags not understood by other third-party tools, and now we can read files missing some required records.



## New in v 6.7.0.0 - September 2015


- **Rad Studio 10 Seattle support.** Includes support for the new C++32 compiler, and all demos have been revised to support High DPI. APIMate also supports High DPI now.

- **Support for opening xls versions from 2 to 4.** As FlexCel already supported xls 5 and up and Excel 1 doesn't exist for Windows, this completes the support for all versions of xls. While  xls versions from 2 to 4 aren't in wide use, they are still used by other third-party libraries.

- **Enhanced High DPI Support in FlexCelPreview.** Now FlexCelPreview supports High DPI in Windows, besides iOS or OSX as it already did.

- **Breaking Change: Property Resolution in FlexCelPreview has been removed.** The property Resolution of FlexCelPreview has been removed because now FlexCelPreview automatically adjusts to the resolution of the monitor.

- **Full support for background images in a sheet.** XlsFile adds two new methods to deal with background images in a sheet: SetSheetBackground and GetSheetBackground. Background images are now converted between xls and xlsx. ApiMate will also report the code to add a background image to a sheet. A new property ExportSheetBackgroundImages allows you to print or export the background images. (note that Excel never prints the background images, so this property is false by default)

- **Full support for manipulating Custom XML parts with XlsFile.** The new methods CustomXmlPartCount AddCustomXmlPart, GetCustomXmlPart and RemoveCustomXmlPart in XlsFile allow for reading and writing the custom xml files of an xlsx files, as explained here: [https://msdn.microsoft.com/en-us/library/bb608618.aspx](https://msdn.microsoft.com/en-us/library/bb608618.aspx)
ApiMate will now show how to enter custom xml parts in an xlsx file.

- **New property for PDF files: InitialZoomAndView.** The new InitialZoomAndView property allows you to specify the initial page and zoom when opening the document.

- **New property for PDF files: PageLayoutDisplay.** The new PageLayoutDisplay property allows you to specify if to display one or two pages, and continuous scrolling  or one page at a time when opening the document.

- **Two new modes for PDF files PageLayout.** Now generated PDF files can use a PageLayout of TPageLayout.OptionalContent to show the optional content panel, or TPageLayout.AttachmentPanel to show the attachments panel.

- **New property ScreenScaling in XlsFile.** This new property allows you to workaround Excel bugs when working in high dpi displays. For more information read [https://www.tmssoftware.com/site/blog.asp?post=311](https://www.tmssoftware.com/site/blog.asp?post=311)

- **Better handling of stored numbers in xlsx.** Now numbers are saved in xlsx with a roundtrip format, which ensures the number we write in the file is exactly the same number that will be read.

- **Ability to &lt;#insert> empty names in reports.** Now when you use the &lt;#include> tag in a report, you can leave the name to include empty. This will mean to insert all the used range in the active sheet.

- **New overload for XlsFile.DeleteRange.** There is a new option for XlsFile.DeleteRange, which will clear the cells but not the formats on it: It will behave similar to when you press "Delete" in a range of cells in Excel.

- **New property ExportEmptyBands in FlexCelReport.** ExportEmptyBands replaces the existing ExportEmptyRanges property which has been deprecated. It allows you to choose between 3 possibilities when the data table has 0 records: Delete the range and move cells up, clear the data and format of the range, or clear only the data.

- **Bug Fix.** Now FlexCel will make sure the xml declaration in the custom xml parts added with AddCustomXmlPart have the same encoding as the encoding being used to store the file.

- **C++ builder support for Android and iOS.** Now we ship the needed hpp files to compile from C++ builder in Android and iOS

- **Bug Fix.** Added workarounds for bugs in XE8 iOS64 compiler. Some things weren't working properly in iOS 64 bits.

- **Bug Fix.** Xlsx files with external formulas referring to other sheets starting with a number weren't quoted, and Excel would report an error when opening those files.

- **Bug Fix.** FlexCel would fail to load files with formulas which pointed to tables in other files with the new table formula syntax.

- **Breaking Change: Improved lookup tag in reports.** The &lt;#lookup> tag in reports has been rewritten to be faster and behave better. IF you are defining your own VirtualDataSets and overriding the Lookup function you might need to rewrite it, as parameters changed. But with the new base lookup implementation that is now available for all, you might just remove the override and use the base.

- **Bug Fix.** Subtotal function could recalculate wrong in border cases.

- **SPLIT Datasets in Reports can now be used as datasets for sheets.** This allows you to overflow a report into multiple sheets. When the data in a sheets reaches the maximum of the split, it will continue in a different sheet. A new sample "Overflow sheets" shows how to do it.

- **Copy to clipboard wasn't working in Excel 2013.** We modified the clipboard format so now it is working.

- **Bug Fix.** When inserting or deleting columns, array formulas located in other sheets might not update to take in account those changed rows or columns.

- **Bug Fix.** Sometimes when moving a range array formulas which pointed to that range might fail to update.

- **Bug Fix.** Some functions with array arguments could not be calculated correctly when the formula was not an array formula.

- **Mobile demos for XE8 were separated from XE7.** Now we have separate XE7 and XE8 firemonkey mobile demos, because by using the XE7 demos in XE8 there was no easy way to add iOS64 as a target.

- **Bug Fix.** The lookup tag introduced in 6.6.32 could fail if the lookup value was a tag in the template

- **Bug Fix.** The functions SumIfs, AverageIfs and CountIfs could give wrong results in some cases.

- **Bug Fix.** When rendering a chart with an image inside, there could be an exception.

- **Bug Fix.** Images inside charts with negative coordinates weren't rendered.

- **Bug Fix.** Now scatter charts behave like Excel, and if any of the x-axis values is a string, it will be rendered as a line chart instead.

- **Bug Fix.** XlsFile.SetAutoRowHeigth wouldn't work if the row was empty.

- **Bug Fix.** The tag &lt;#db.\*> wasn't working in reports from TList&lt;> . Now &lt;#db.\*> will only output public or published properties of the class, not the methods.

- **Bug Fix.** Chart rendering now renders charts where all values are 0.

- **Bug Fix.** Chart rendering now respects the label positions next to axis, high and low.

- **Bug Fix.** ExportEmptyBands introduced in 6.6.25 wouldn't work in detail reports.

- **Bug Fix.** In some cases when generating reports and exporting them to pdf directly without saving them as xls/x, there could be a range check error.

- **Bug Fix.** Tabs inside text in  autoshapes now will render as 8 spaces. (note that we don't use the tab definitions from the autoshape, so this is an approximation)

- **Breaking Change: Bug Fix.** Implemented a workaround for bad GDI+ header files in Delphi which could cause crashes in 64 bit. Now you need to pass a NativeInt (or ULONG_PTR) instead of  a Cardinal (or ULONG) to  FlexCelDllInit and FlexCelDllShutdown, if you are using those methods.

- **Bug Fix.** When exporting to bitmaps, the bitmaps where a little bigger than the page size

- **Bug Fix.** Sometimes the TFlexCelPreviewer component could show wrong borders when showing all sheets.

- **Bug Fix.** TUIImage.ToNativeImage didn't work in FireMonkey.

- **Improved compatibility with invalid xlsx files generated by third parties.** FlexCel can now read some invalid formulas written in xlsx by other third-party products.



## New in v 6.6.23.0 - April 2015


- **Setup now warns if the Android SDK isn't installed in XE8.** In XE8 the Rad Studio setup doesn't install the full Android SDK. You need to manually compile an app from inside the IDE to get all the packages. Now the FlexCel setup will warn you if you try to install for Android in XE8 and haven't compiled an app before.

- **Bug Fix.** Delphi resource compiler could fail to build localized apps when using FlexCel.

- **Bug Fix.** There could be an error when rendering error bars in charts and there were missing values.



## New in v 6.6.22.0 - April 2015


- **Rad Studio XE8 support.** FlexCel now supports Rad Studio XE8

- **iOS 64 bit support.** FlexCel now supports the new iOS 64 bit platform introduced in XE8.

- **New property SheetView in XlsFile allows you to set the page view mode and zoom for each mode.** Now you can see or set the page view mode in a sheet (normal, page layout or page break preview). You can also specify the zoom for each of the modes. As usual, APIMate will show you the syntax.

- **New property LinksInNewWindow for FlexCelHtmlExport and FlexCelSVGExport.** When you set LinksInNewWindow to true, both FlexCelHtmlExport and FlexCelSVGExport will export the hyperlinks in the file to open in a new window.

- **Links to local files and to current workbook are now exported in TFlexCelHtmlExport.** Now links to local files or other cells in the current workbook are exported to html. This allows for navigating inside a file. Links in the current workbook work even when exporting to different tabs.

- **Breaking Change: XlsFile.AddImage(row, col, TUIImage) now takes in account the declared image dpi.** Now if you are calling AddImage without specifying the dimensions, FlexCel will use the dimensions corrected by the dpi declared by the image. This is the same way Excel works. In previous FlexCel versions we always assumed a 96dpi image.

- **Rendering of error bars in xls charts.** Now when exporting to pdf/html/etc, FlexCel will draw error bars. All modes (StdErr, StdDev, fixed, percent, custom) are supported.

- **Improved display of line charts.** Now colors and sizes of lines in xls charts will be read from the new xlsx records on it if they exist. This leads to a more faithful rendering, because the xlsx records have extra information, like for example a line width that isn't restricted to 4 sizes.

- **TXlsNamedRange.GetRanges is now public and documented.** GetRanges will return an array with the ranges composing a name. So if you for example have a name with the range "1:1, A:A", GetRanges will return an array with 1:1 and A:A. This method can be used to parse the PRINT_TITLES range.

- **Improved display of markers in charts.** Now markers in charts render much more alike Excel 2013, with the new options for images, etc.

- **Bug fix.** XlsFile.FillPageHeaderOrFooter could return an extra "&" character at the end in some cases.



## New in v 6.6.21.0 - January 2015


- **Improved Setup.** Now the registered setup includes the binary dcus for the latest Delphi version (XE7 at the time of writing this), resulting in a much faster setup for those users.

- **New UsePrintScale property in FlexCelHtmlExport.** If you set the new property FlexCelHtml.UsePrintScale to true, then the exported html will use the scaling of the printed sheet instead of being exported at 100% zoom.

- **Bug fix.** Some JPEG images weren't recognized as such.

- **Bug fix.** Reports might not read expression values when tags had a default value, like &lt;#value;0>

- **Improved APIMate.** Now APIMate produces better Delphi and C++ code.

- **Bug fix.** Sometimes FlexCel could fail to load an xlsx file with different images with the same extension but different case (like image1.png and image2.PNG)

- **Fixed linking in C++ builder 32bits when using FlexCelReport and not runtime packages.** We added a workaround for bug: [http://qc.embarcadero.com/wc/qcmain.aspx?d=99647](http://qc.embarcadero.com/wc/qcmain.aspx?d=99647)  (Rad Studio &lt; XE6). Now it should be possible to link FlexCelReport in C++ builder 32bit apps.

- **New parameters in FlexCelPdfExport.AfterGeneratePage and BeforeGeneratePage events.** The new parameters are the XlsFile being exported, the FlexCelPdfExport component doing the export, and the current sheet.

- **Improved RecoveryMode.** Now FlexCel can recover more types of wrong files when RecoveryMode is true.

- **New "Features" demo for reports.** This demo shows how to load images on demand in a report, and other interesting things like how to use a SheetSelector.

- **When drawing xls charts, we now use the options for not plotting empty cells.** This option was introduced in Excel 2007, and FlexCel was ignoring it. Now if you choose not to ignore hidden rows or columns, the chart will render as expected.

- **New method XlsFile.RemoveUserDefinedFunction.** XlsFile.RemoveUserDefinedFunction allows to unregister a previously registered UDF for recalculation.

- **Breaking Change: Now when drawing chart labels that have N/A! error as result, FlexCel won't draw them.** Excel 2003 or older  is different in the way it draws #NA! errors in chart  labels from Excel 2007 or newer. In older Excel versions, the label would just draw as #NA!. In newer Excel versions, it doesn't draw. To be consistent with more modern Excel versions, now FlexCel won't draw them either when exporting to pdf or html.

- **Now FlexCelDocExport is compatible with C++ builder.** Now you can use the mobile component FlexCelDocExport in C++ builder mobile applications.

- **Bug fix.** In some cases, when pasting a file with autofilters from Excel you could get a range error. This is because Excel copies the filter in its totality and part of the filter might be outside the range copied. Now FlexCel will resize the autofilter if it extends beyond the copied range.

- **Bug fix.** FlexCelReport might not  filter datasets in the config sheet when they were the master.

- **Fixed memory leak in FlexCelReports that happened when some Exceptions were raised.** In some cases where an exception happened in a particular place while generating a report, there could be a memory leak.



## New in v 6.6.11.0 - December 2014


- **Support for recalculating 31 new functions introduced in Excel 2013.** Support has been added for: DAYS, ISOWEEKNUM, BITAND, BITOR, BITXOR, BITLSHIFT, BITRSHIFT, PDURATION, RRI, ISFORMULA, SHEET, SHEETS, IFNA, XOR, FORMULATEXT, COT, ACOT, COTH, ACOTH, CSC, CSCH, SEC, SECH, ARABIC, BASE, DECIMAL, COMBINA, PERMUTATIONA, MUNIT, UNICHAR, UNICODE

- **Subtotal command in XlsFile.** There is a new command xls.SubTotal(...) which works the same as the command "Subtotal" in the Excel Ribbon, "Data" tab. While you shouldn't use this when creating new files, it can be useful for formatting old files. For new files, it is best to just create the subtotals in place.

- **New option "ExcelLike" in XlsFile.Sort.** Now when doing a XlsFile.Sort command you can choose between the correct way to handle formulas (this was the only option before) or the "Excel" way of handling formulas, where references are not updated when a row is moved of place in the sort. The ExcelLike mode doesn't adapt formulas that reference those rows, but it can be much faster for tens of thousands of records.

- **New methods IsRowMarkedForAutofit and IsColMarkedForAutofit in XlsFile.** The new methods will return true if a row or column was marked for autofit.

- **New property ExcelFile.AllowEnteringUnknownFunctionsAndNames.** If you set this property to true, you will be able to enter unknown functions inside formulas, like "=SomeText()". Excel will show the result as a #NAME! error. When this property is false (the default) FlexCel will raise an Exception if the name is not know, which is better to detect misspells.

- **New properties XlsFile.RecalcVersion and FlexCelReport.RecalcVersion.** This new properties allow you to specify the Excel version that last calculated the file. If you set it to for Example Excel 2010, any Excel newer than Excel 2010 will recalculate the file on open, and ask for saving changes when you close the file. Excel 2010 or older won't recalculate the file on open. If you want every version of Excel to recalculate on open set this property to AlwaysRecalc (the default). Look at the API developers guide for more information.

- **Breaking Change: XlsFile.RecalcForced and FlexCelReport.RecalcForced properties have been removed.** RecalcForced used a way to make files recalculate on open which has been deprecated in newer versions of Excel, and will cause validation errors with the generated files. For this reason, RecalcForced wasn't doing anything in the last couple of years.
Look at the new RecalcVersion property if you were using RecalcForced and want new not deprecated way to create files which Excel will recalculate on open.

- **Included reports can now reference the formats of the parent report.** Now an included report can reference the formats of the parent report, same way as it can reference the expressions.

- **New overloads of XlsFile.GetObjectProperties and XlsFile.GetObjectAnchor that take an object path.** This new methods allow you to access the properties and anchor of an object by specifying its name, as in Xls.GetObjectAnchor(-1, "@MyObject")

- **Autofitting columns  with 90 degree rotation would work always as if the column had "Wrap text" enabled.** When autofitting columns which had a rotation of 90 degrees, FlexCel would always try to wrap the text so it fitted in many lines, even if the cell wasn't set to wrap. Now it will only do this if the cell has "Wrap text" on.

- **Pivot tables in xlsx are now copied when you copy sheets.** Now if you InsertAndCopySheet(...) a sheet with a pivot table from an xlsx file, the table will be copied. (pivot tables in xls were already copied)

- **Unknown names in formulas now return #NAME! instead of #NA!.** Now when a formula references a name that doesn't exist, FlexCel will return #NAME! as the formula result, instead of #NA! as it used to do.

- **Bug Fix.** When using a user-defined function twice with a FlexCel Report, the memory would be freed twice.

- **Bug fix.** When setting the text of an object using SetObjectText the font might not be preserved.

- **Bug fix.** When changing the font in HtmlFont event in TFlexCelHtmlExport there could be an Exception.

- **Bug fix.** RoundUP and RoundDown functions could return the same number and not the rounded up number in some cases when the number of digits was negative.

- **Bug Fix.** Rendering some files with thousands of hidden columns could take too long.

- **Improved C++ Builder support.** Some public interfaces didn't define a GUID, and that made them unusable from C++ Builder. Now all public interfaces define a GUID.

- **Hidden rows could sometimes count when finding the maximum used column in the sheet.** When printing or exporting an xls/x file, a hidden row with columns outside the printing range could in some cases cause the maximum column to be that in the hidden row, which wouldn't be printed.

- **Improved compatibility with invalid xls files.** Now FlexCel can read some more invalid xls files created by third parties.

- **Sheet names aren't always quoted when returning formula text.** In older FlexCel versions, the sheet was always quoted in formulas. So if you retrieved for example the formula in A1, it could be 'Sheet1'!A2. Now we quote the sheet only if needed, same as Excel does. So we would return Sheet1!A2 instead.

- **New convenience constructor for XlsFile which takes a Stream.** Now you can create an XlsFile and open a stream in a single operation, without having to first create the XlsFile and then call xls.Open.

- **Improved error message when opening files with 0 bytes.** Now when opening files with 0 bytes or streams with the position at the end, FlexCel will say a clear message instead of saying that the file format isn't Excel or newer.

- **New properties TFlxConsts.MaxRowCount and TFlxConsts.MaxColCount.** Those properties return TFlxConsts.Max_Rows + 1 and TFlxConsts.Max_Columns + 1 respectively. Max_Rows and Max_Columns were zero based, so for example Max_Rows return 65535 for xls and not 65536 which is the row count. The new properties return the one-based maximum, which makes it simpler to work in the one-based FlexCel API.



## New in v 6.6.2.0 - October 2014


- **FlexCelPrintDocument now supports FireMonkey in Windows.** Now you can print natively form any FireMonkey for Windows application using FlexCelPrintDocument, same as you could in VCL before. Note that only Windows is supported. For iOS and Android, as the native printer format is PDF, to print just export to PDF and share the file with FlexCelDocExport, as shown in the examples.

- **Better support for TList&lt;interface> in reports.** Now FlexCel fully supports TList&lt;interface> as data sources for reports. Note that for this to work, the interface must be compiled with {$M+}. Also, you can only call methods of the interface, not properties since properties don't have RTTI.

- **Improved ReportConverter.** The report converter for FlexCel 3 reports does a more faithful conversion now.

- **Better rendering of text in rotated shapes.** In Excel 2003 or older, text in rotated shapes was shown without rotation and that's how FlexCel would show them. Since Excel 2007 the text can rotate with the shape, using an undocumented record in xls. Now FlexCel can read it and  will honor that setting when converting to pdf/html/svg/printing/etc.

- **Bug Fix.** A local link in a pdf to a page that wasn't exported could cause an Exception.

- **Bug Fix.** Exporting "Center on selection" cells could be too slow in border cases.

- **Bug Fix.** XlsFile.SetCommentRow could set the wrong comment in some cases.



## New in v 6.6.1.0 - October 2014


- **Generic reports using &lt;#table.*> can now use user defined functions.** Now you can apply a user defined function to a &lt;#table.*> tag.

- **Generic reports using &lt;#table.*> can now reference fixed fields in the table.** Now you can mix &lt;#table.field> with &lt;#table.*> in the same cell.

- **Better compatibility with files created by third parties.** Now FlexCel will load invalid xlsx files with repeated comments.

- **Bug Fix.** Setup could fail to install if you only had C++ Builder and not Delphi installed.

- **Bug Fix.** Generated xlsx files could be invalid when removing frozen panes from an existing file.



## New in v 6.6.0.0 - October 2014


- **Reports.** FlexCel for VCL has now a fully featured reporting engine, similar to the already available in FlexCel.NET.  You can now generate files by writing tags in Excel and having FlexCel replace those tags for you. Take a look to the over 30 new demos in the "Reports" section.

- **New Setup doesn't modify system path.** The setup will now create symbolic links to the FlexCel BPLs from the FlexCel folder to the Delphi BPL folder, so Windows can find FlexCel BPLs. Windows path won't be modified anymore.

- **New MigratingFromFlexCel3.pdf document.** The new document explains in detail what is needed to migrate from FlexCel 3.

- **New unit FlexCel.Core to make easier to share VCL/FireMonkey code.** Before this version, you had 2 different units: VCL.FlexCel.Core and FMX.FlexCel.Core which you had to use depending in the platform. Now, while you still need to use at least once FMX.FlexCel.Core or VCL.FlexCel.Core (it might be in your main project), in all the other units you can use the platform agnostic "FlexCel.Core", and avoid using IfDefs.

- **Breaking Change: Now the result of ShapeOptions.Text is a TDrawingRichString instead of a TRichString.** In order to allow more customizability in the text of shapes and objects, we had to move the text property from a TRichString (which is used for cells, and in xls was also used for objects) to a TDrawingRichString (Which in xlsx offers more possibilities to customize the text). As there is an automatic conversion from a TDrawingRichString to a TRichString, most code will just keep working. But there might be some cases (like functions where you pass a var parameter) where you will need to change the types form TRichString to TDrawingRichString in order to compile.

- **Better support for preserving autoshape text in xlsx.** Now when you change the text of an autoshape in xlsx, the existing properties of the text will be preserved.

- **Support for reading and writing a cell's text direction (RTL, LTR or Context).** Now you can specify the text direction in a cell, and APIMate will show you how to do it. The FlexCel rendering engine also now supports better RTL code (still without providing official RTL support, it is better in this version and usable in most cases)

- **Support reading the number of horizontal and vertical page breaks in a sheet.** Two new properties: XlsFile.HPageBreakCount and XlsFile.VPageBreakCount return the count of page breaks in a sheet.

- **Bug Fix.** XlsFile.LastFormattedCol returned the last formatted column - 1. Now it is returning the correct number.

- **Bug Fix.** Rendered xls charts could show an extra line in some corner cases with missing data.

- **Bug Fix.** FlexCel would fail to read CDATA sections in tags written by third-party tools.

- **Bug Fix.** Macro references in buttons could be copied wrong when copying sheets.

- **Bug fix.** When copying a range of cells to another sheet which included formulas introduced in Excel 2007 or newer there could be an error when saving as xls.

- **Bug Fix.** FlexCel enforced a maximum of 1023 manual page breaks for xls but not for xlsx. Now We also check that the generated xlsx files don't have more than 1023 manual page breaks, since that would crash Excel.

- **Bug Fix.** FlexCel used to embed a resourcestring of a single quote " which was crashing the localizer in Delphi. Now we include it as a constant.



## New in v 6.5.0.0 - September 2014


- **Rad Studio XE7 Support.** Rad Studio XE7 is now supported. FireMonkey demos have been rewritten to use the new FireUI designer.

- **PDF/A support.** FlexCel can now export to PDF/A-1, PDF/A-2 and PDF/A-3 files. A new property FlexCelPdfExport.PdfType determines if the file is a standard PDF or the version of PDF/A.

- **Breaking Change: Generated PDF files are now tagged by default.** The files generated by FlexCel are now tagged by default, as tagging is an accessibility requirement. Tagged PDF files are bigger than normal files so in order to try to get smaller files FlexCel uses now features available only in Acrobat 7 or newer. To go back to generating untagged files you can set FlexCelPdfExport.TaggedPdf = false. To go back to creating files compatible with Acrobat 5 or newer, set FlexCelPdfExport.PdfVersion = TPdfVersion.v14

- **Breaking Change: Generated PDF files are now compatible with Acrobat 7 or newer.** In order to reduce the size of the tagged pdf files that FlexCel now creates by default, FlexCel now generates files that need Acrobat 7 or newer to open. To go back to creating files compatible with Acrobat 5 or newer, set FlexCelPdfExport.PdfVersion = TPdfVersion.v14. Note that as PDF/A-1 requires compatibility with Acrobat 5 or newer, when exporting PDF/A-1 FlexCel will use v14 automatically. PDF/A-2 and 3 don't require v14, so it isn't used by default for those formats.

- **Breaking Change: Generated PDF files now embed the fonts by default.** Now the default value of FontEmbed in FlexCelPdfExport and PdfWriter is TFontEmbed.Embed. While this will create slightly bigger files, they will show fine everywhere, including mobile devices which might not have the fonts. You can revert to the old behavior by changing FontEmbed to be TFontEmbed.None.

- **Breaking Change: FlexCel will throw an Exception when trying to embed a font that doesn't have a license allowing embedding.** FlexCel will now check that the embedded fonts in PDF have a license that allows embedding. You can revert to the old behavior by setting UnlicensedFontAction = TUnlicensedFontAction.Ignore, in case you have an agreement with the Font author. You can also set UnlicensedFontAction = TUnlicensedFontAction.Replace to replace the unlicensed fonts with a fallback font. FlexCelTrace will alert when replacing or ignoring a font that is not licensed.

- **Ability to embed files inside the PDF.** Now you can embed arbitrary files inside the pdf. This allows for example to ship the original xls/x file inside the pdf. This is supported also in PDF/A-3.

- **Ability to set the language of the PDF files.** You can now set a FlexCelPdfExport.Properties.Language to specify the language of the generated PDF file. Note that the language will be used by text-to-speech engines to read text out loud, so it is recommended to set this property.

- **PDF properties are now saved in XMP format.** PDF properties (like Author, Title, etc.) are now saved in XMP xml format besides the PDF format. XMP is a requirement for PDF/A, and allows other tools that don't understand PDF to read the metadata. Note that the files generated by FlexCel will be now a little bigger due to this metadata, because it can't be compressed.

- **Ability to embed a Color Profile inside the generated pdf files.** You can now set a FlexCelPdfExport.EmbedColorProfile property to embed a color profile in the generated files. Note that as a color profile isn't required and it increases the size of the generated files, this option is false by default. But as it is required by PDF/A, a color profile will be embedded in PDF/A files.

- **Breaking Change: Now if you don't specify properties for pdf files in FlexCelPdfExport (like Author, Title, etc.), those will be read from the Excel file being exported.** If you want to revert to the old behavior, you can set UseExcelProperties = false in FlexCelPdfExport.

- **New structure StandardMimeType returns the mime types for xls, xlsx, xlsm, pdf, etc.** You can use StandardMimeType where you need to specify a mime type for a file generated with FlexCel, instead of having to manually search for the type.

- **Improved Search and Replace.** Now FlexCel preserves better the format of the cells being replaced. A new overload of XlsFile.Replace allows you to specify the format or the values of the replaced cells in a cell by cell basis.

- **Support for entering names referring to other files using Excel notation.** A normal reference to another file has the filename inside brackets, like "[file1.xlsx]Sheet1!A1". But in the case of global names, Excel uses the notation "file1.xlsx!name1", without brackets, which makes it impossible to know if you are entering a name reference to another file (file1.xlsx) or a name reference to the same file, in a sheet named file1.xlsx. FlexCel didn't allow this way to specify the names, and it used to ask for brackets always so you would have to write [file1.xlsx]!name1 to enter the name. Now you can use the same notation as Excel, and FlexCel will allow it as long as you setup a TWorkbook before which includes file1.xlsx.

- **Support for format strings that specify fractions.** Now when using a format string like "??/??" the numbers will be displayed as fractions. For example 0.75 will show as 3/4. All Excel formats for fractions are fully supported.

- **New constructor for XlsFile allows to specify the Excel version in one step.** Now you can create a new file in for example Excel 2010 file format by writing XlsFile xls = new XlsFile(1, TExcelFileFormat.v2010, true); in C# or  xls := XlsFile.Create(1, TExcelFileFormat.v2010, true); in Delphi.

- **New enumeration TExcelFileFormat.v2013.** We now provide a specific TExcelFileFormat.v2013 enumeration to create Excel2013 files.

- **iOS and OS/X previewer compatibility improved.** Some xlsx files generated by FlexCel that wouldn't show in iOS/OSX previewer will display now. Xlsx charts now update their caches so the previewer will show them correctly.

- **TFlxApplyFont as a new StyleEx property that allows for fine control of which styles are applied.** Before this release you could only apply the full style of the font or nothing by changing the Style property. Now you can specify individual styles like bold or italics by changing the StyleEx property.

- **XlsFile.Sort does a stable sort.** Now when you sort a range of cells, order will be preserved for items with the same values.

- **Bug Fix.** Local named ranges could lose their sheet when inserting sheets from other file.

- **Shapes inside charts are now preserved in xlsx files..** Now xlsx charts will preserve the shapes inside.

- **Improved image rendering.** Some files created by third parties could display the images in the wrong position.

- **Ability to preserve modification date in xlsx files.** By default, FlexCel will set the modification date to the date the file was saved. But if you are modifying an existing file and want to preserve the original creation date, you can now do it by setting XlsFile.DocumentProperties.PreserveCreationDate to true.

- **Better support for Excel 4.0 macro sheets.** Files with Excel 4.0 macros should load better.

- **Bug Fix.** XlsFile.Replace might not keep existing cell formats when replacing dates.

- **Bug Fix.** Some files could trigger an AV when deleting comments.

- **Bug Fix.** Chart.DeleteSeries could break the format of the remaining series when called in a serie at the middle of the chart.

- **Bug Fix.** There could be an exception when deleting some ranges of cells with hyperlinks.

- **Bug Fix.** Negative dates when in 1904 mode used to display as ####. Now they display as in Excel (see [http://support.microsoft.com/kb/182247](http://support.microsoft.com/kb/182247) ). Note that this is not a logical way to display dates, that is -1 doesn't mean 12/31/1903, but it means "-1/2/1904". Negative dates actually increase as the number get smaller.

- **Support for UTF16 surrogates when exporting to pdf.** Now when exporting to pdf, FlexCel will correctly display UTF16 surrogates. FlexCel already was surrogate-aware in the rest of the codebase.

- **Support for space (" ") named styles.** While Excel won't let you enter a cell style named " ", it will allow you to use it if you manually edit an xlsx file and create it there. To be able to deal with those files, FlexCel will now support reading and writing styles named with a space.

- **Now when adding controls with linked cells, the linked cells will be modified to match the initial value of the control.** Now when adding comboboxes, listboxes or checkboxes linked to a cell, the cell will be modified to match. Note that the change applies to newly created objects, if you change the value of an existing control, the linked cell was always updated in all FlexCel versions that supported changing control states.

- **Bug Fix.** Some xlsx files with charts could enter an infinite loop when loading.

- **Bug Fix.** When replacing rich strings, the rtf runs  could be wrong in border cases.



## New in v 6.3.0.0 - April 2014


- **Rad Studio XE6 Support.** Now FlexCel supports Rad Studio XE6.

- **SVG Exporting.** A new component, FlexCelSVGExport allows to export xls/x files to SVG. A new example "Export SVG" is included too. SVG files are now supported by all major browsers, desktop and mobile, so you can use them when exporting to html to have resolution independent images.

- **HTML 5 Exporting.** Now FlexCelHtmlExport can export to HTML5/CSS3 as one of the options. When exporting to HTML5 some new capabilities are available.

- **Improved support for document properties.** Full support for setting standard or custom properties in xlsx files. (xls is still read only). A new method XlsFile.DocumentProperties.RemoveAllProperties will allow you to remove all properties in the xls or xlsx files, so you can be sure it doesn't contain unwanted information. A new method XlsFile.DocumentProperties.GetUsedStandardProperties will return a list of the used standard properties in the file.  A new method XlsFile.DocumentProperties.SetStandardProperty allows to modify standard properties in xlsx. New methods SetCustomProperty, GetCustomProperty and GetAllCustomProperties allow to manage custom properties.
Document properties will be preserved when opening xls or xlsx files and saving as xlsx, or when opening and saving as xls. They won't be preserved when opening xlsx and saving as xls.

- **Embed images in HTML files.** A new property: FlexCelHtmlExport.EmbedImages allows to embed the images as Data Uris ( [http://tools.ietf.org/html/rfc2397](http://tools.ietf.org/html/rfc2397) ) inside the html file. When setting this property to true the generated html file can be self contained, and you don't have to deal with managing the external images.

- **SVG images in HTML  files.** Now FlexCelHtmlExport.SavedImagesFormat allows a new possibility: THtmlImageFormat.Svg.  SVG is a standard vector image format supported by most modern browsers, and using svg means that high-dpi/retina devices can zoom smoothly in the vector assets of the file, like charts or autoshapes.

- **TExcelChart.RemoveLegend method.** A new method in TExcelChart allows to remove a legend. Note that currently this only works in xls charts, not xlsx.

- **Improved chart rendering.** Now charts will have the frame box with rounded corners if you specify so in Excel.

- **Improved performance in VLookup.** The implementation of the function VLookup is now much faster when searching in an unsorted range.

- **Improved performance in pdf/html exporting.** Many optimizations in the rendering engine.

- **Improved APIMate.** APIMate now shows how to autofit a comment box to the text size, and also how to set properties in xlsx.

- **Bug fix.** Some cells with automatic background colors in xls files could be saved with the wrong color when converting to xlsx.

- **Bug fix.** XlsFile.Find could keep returning the same values in corner cases.

- **Bug fix.** When Inserting an empty sheet locally defined ranges wouldn't update the sheet where they were defined. This happened only with empty sheets, if you inserted a sheet with data it would work fine.

- **Bug fix.** FlexCelPreview could show text as underlined in some third-party generated xlsx files.



## New in v 6.2.0.0 - February 2014


- **Support for preserving PowerPivot tables in xlsx.** Now PowerPivot tables will be preserved in xlsx.

- **New methods FlexCelDllInit and FlexCelDllShutdown.** These new methods are designed to be called when you encapsulate FlexCel inside a dll. You need to call them from inside your main application before calling any methods in the dll. They will initialize and shutdown GDI+, as that needs can't be done from the dll itself.

- **Improved Excel 2013 support.** FlexCel could fail to open some complex Excel 2013 xlsx files.

- **Improved handling of dates between 1900-1-1 and 1900-2-28.** Excel considers 1900 to be a leap year, even when it wasn't. ( look at [http://support.microsoft.com/kb/214326](http://support.microsoft.com/kb/214326) ) As FlexCel uses the .NET DateTime which correctly assumes 1900 wasn't a leap year, dates between 1900-1-1 and 1900-2-28 would appear in FlexCel as one day before the dates in Excel. Now FlexCel corrects those dates so they look as in Excel, but the DateTime datatype still doesn't have Feb-29-1900, so that date will still be wrong. It is still advised to not use dates before march-1-1900 when working in Excel.

- **Support for running in machines with FIPS 140 enabled.** Now FlexCel can be used in machines with FIPS 140 policies enforced. ( see [http://support.microsoft.com/kb/811833](http://support.microsoft.com/kb/811833) )

- **Improved rendering of formatted numbers.** Some formatting strings (for example "general;-general") were not rendered like Excel.

- **Improved default font in Headers and footers.** In previous versions if no font was specified for the headers or footers, FlexCel would default to Arial. Now it defaults to the normal font in the file.

- **Support for displaying numbers in Engineering notation.** When displaying numbers in Scientific notation, FlexCel would always use normalized notation ( [http://en.wikipedia.org/wiki/Scientific_notation#Normalized_notation](http://en.wikipedia.org/wiki/Scientific_notation#Normalized_notation) ). Now it can also use Engineering notation if the format string specifies it ( [http://en.wikipedia.org/wiki/Engineering_notation](http://en.wikipedia.org/wiki/Engineering_notation) )

- **iOS and Android pdf encoding handling.** Now FlexCel will create pdf files without using Win1252 encoding, which isn't included by default in Xamarin for iOS or Android.

- **SheetProtection is copied when copying sheets from one file to another.** Now FlexCel will copy the sheet protection when you are copying sheets from other file object.

- **Bug fix.** The rendering engine could fail to draw the top gridline in pages after the first when PrintGridLines was true and you were repeating rows at the top.

- **Bug fix.** When opening xls files with data validations and saving them as xlsx, some relative ranges could point to an incorrect cell range in the xlsx file.

- **Bug fix.** Charts in xlsx files didn't preserve textures.

- **Bug fix.** There was an error when recalculating the =LARGE and =SMALL functions in non contiguous ranges of cells.

- **Bug fix.** GDI+ could fail to work in Windows Server 2008 R1, due to a bug in the VCL.

- **Bug fix.** Sometimes AddFormat() could repeat a format twice in the file.

- **Bug fix.** In certain cases when a macro name had a dot "." on it, FlexCel could fail to open the file.

- **Improved 3rd party compatibility.** Improved generated xls files so they can be loaded by some 3rd party tools.



## New in v 6.1.1.0


- **Ability to change the sheet codename.** When the file has no macros, now FlexCel will allow you to change the codename, not only read it. Also now when calling ClearSheet, the codename is not changed.

- **Improved C++ builder support.** Fixed pragma links for handling all combinations: 64/32 bits, OSX/Windows, with runtime packages or without. If you were using pragma links to FlexCel in your code before, you should be able to remove them all now.

- **Bug fix setting Autofilters.** A very specific combination of setting and unsetting autofilters could raise an AV.



## New in v 6.1.0.0 - September 2013


- **Rad Studio XE5 and Android support.** FlexCel can now run in Android with XE5. In includes a native Android canvas (not FireMonkey) for maximum performance, same as the other native canvas for iOS, Windows and OSX.

- **Improved chart rendering.** While the chart engine still can only draw charts in xls files at the moment, it can now read some embedded xlsx records in the xls file so the chart will display like Excel 2007 or newer, not like Excel 2003.

- **Improved xlsx autoshape rendering and conversion.** Now autoshapes in xlsx files are converted better to xls, and also render more faithfully.

- **Improved rendering in iOS and Android.** Now texture bitmaps are also supported in iOS and Android besides Windows.

- **iOS7 support.** Changes to better support iOS7.Some records in xlsx files have been changed so the iOS7 viewer can show the files.

- **New static events in TPdfWriter.** There are 3 new static events: GetFontDataGlobal, GetFontFolderGlobal, OnFontEmbedGlobal. Those work like the already existing GetFontData, GetFontFolder and OnFontEmbed, but being static, they work an application level. If you set them, you don't need to set them for every TPdfWriter or TFlexCelPdfExport instance you create.

- **Support for forcing codepage in Excel95.** Now you can force a codepage when opening an Excel 95 file with xls.Open(..., Encoding). While normally you don't need to specify a codepage for xls95 since it is specified in the file, if the file doesn't have a codepage record or has it wrong, you can now specify it here.

- **Bug fixes.** Small bugfixes.



## New in v 6.0.6.0 - September 2013


- **Ability to autofit part of a column or a row.** Now you can autofit a column using for example the data in the first 50 rows, making it faster for huge spreadsheets.

- **Many small fixes and improvements.** Performance tweaks, bug fixes, small improvements.



## New in v 6.0.1.0


- **New TFlexCelFormatSettings allows better control of the locale FlexCel uses for converting numbers to strings.** There is a new TFlexCelFormatSettings class which allows you to change the numeric and date strings like the decimal separator for FlexCel only, no matter what the rest of your application is using. You can change it both for globally for your full application, or for the current thread only. Look at the API guide for more information.

- **New startPageToExport and totalPagesToExport parameters in TFlexCelPdfExport.ExportSheet.** Those methods allow to control how many pages are exported.

- **HotFix for QC 116108.** This is a hotfix for bug [http://qc.embarcadero.com/wc/qcmain.aspx?d=116108](http://qc.embarcadero.com/wc/qcmain.aspx?d=116108) in the OSX/iOS RTL. Without this bug fixed, FlexCel could confuse the named ranges and print the wrong page range. With this hotfix it will behave correctly even without the QC fixed.

- **Fix for Corrupt FireMonkey in Windows preview.** Under some graphics cards, the FlexCelPreview component in FireMonkey for windows could display wrong. This should be fixed now.



## New in v 6.0.0.0 - August 2013


- **XE4 and iOS Support.** Read, write, modify, preview, print and export to pdf your Excel files from any iOS device. New components to export and import files from and to your application. New demos and tutorials on how to create iOS applications using FlexCel.

- **Reduced Memory usage.** FlexCel 6 will use from about 1/2 to 1/4 of the memory FlexCel 5 used. We've done a big rearchitecture of the code to ensure it runs fine in memory-limited devices, and this improvement is also available for Windows.

- **More conformant xls files.** All xls files created by FlexCel now pass the Microsoft Office validator if the original file passed it. Note that not all xls files created by Excel pass the Office validator.

- **In OSX and iOS the pdf engine doesn't need more access to the "Fonts" folder.** Now the pdf engine in OSX and iOS an get the fonts directly from memory.

- **Many small improvements.** In this release we've taken a lot of time reviewing the small details, making the engine a little faster and a little better all around.



## New in v 5.6.10.0 - May 2013


- **New startPageToPrint and totalPagesToPrint parameters in TFlexCelPrintDocument.PrintSheet.** Those methods allow to control how many pages are printed.



## New in v 5.6.9.0


- **New BackgroundColor property in FlexCelHtmlExport.** This allows you to define the background color for empty cells when exporting to html. You can also set it to transparent if you are customizing the html to have a custom background image or texture, so the cells show through it.

- **New Parameter to rename the files created by FlexCelHtmlExport.ExportAllVisibleSheetsAsTabs.** Now ExportAllVisibleSheetsAsTabs has a parameter named "OnSheetName" where you can pass an anonymous method and use it to specify how the filenames for every html file for every tab are created based in the corresponding sheet name.

- **New Macros admitted in the SheetSeparator when exporting all sheets as a single file.** You can now also write &lt;#prevSheetName> and &lt;#prevSheetPos> in the sheet separator, and they will be replaced by the previous sheet name and position respectively.



## New in v 5.6.8.0


- **New DefaultRowHidden property in TExcelFile.** This new property allows you to hide all empty rows in the file.

- **Performance improvements.** VLookup, HLookup, Lookup and SumProduct are faster in recalculations.



## New in v 5.6.7.0


- **New AutofitComment method in TExcelFile.** This new method allows you to resize a comment box so all text fits inside.



## New in v 5.6.5.0 - December 2012


- **XE3 Update 1 support.** This release adds compatibility with the new 64 bit C++ builder compiler.

- **Reduced exe size.** There has been a reduction in the sizes of applications which use FlexCel.

- **Support for recalculating XIRR and XNPV functions.** XIRR and XNPV are now recalculated.

- **Performance enhancements.** Small performance enhancements in different places.



## New in v 5.6.0.0 - November 2012


- **Preview support in firemonkey.** Introducing a new native preview component for firemonkey. Fully styleable, and uses native coregraphics or GDI+ depending on the platform for better performance. See the new "Custom preview" demo in firemonkey. Note: Printing in firemonkey is not yet available.

- **Bug fixes.** Many small bug and stability fixes.



## New in v 5.5.0.0 - October 2012


- **INTELLIGENT PAGE BREAKS.** Even when there is no direct support for widow/orphan lines in Excel, FlexCel now provides a way to keep rows and columns together avoiding page breaks in the middle of important data.
 You tell FlexCel which rows you want to keep together, and it will automatically add page breaks at the needed points in the file so it prints as you want to. This new feature can be used both from the API or from the reports. For more information, look at the "Intelligent Page Breaks" demos in the Report and API sections.

- **Rad studio XE3 Support.** Rad studio and Firemonkey 2 are supported.

- **Native exporting of xls/x files to pdf.** Now FlexCel can export any xls/x file to pdf. Export is native, and no third-party dlls, Excel or Acrobat are needed. Charts are exported in xls, not yet in xlsx.

- **Native exporting of xls/x files to html.** Now FlexCel can export any xls/x file to fully standards compliant html. Also it can create MHTML files, that can be used for sending html email.

- **Native previewing of xls/x files.** Now FlexCel can preview any xls/x file as it would be printed. Previewing is not yet available in FireMonkey.

- **Native printing of xls/x files.** Now FlexCel can natively print any xls/x file. Printing is not yet available in FireMonkey.

- **Support for reading and writing encrypted xls and xlsx files.** Support for Excel 95, 2003, 2007, 2010 and 2013 encryption modes. Encryption is available only in Windows, 32 or 64 bits, Firemonkey or VCL. Not yet in OSX.

- **AUTOFITTING SUPPORT.** Now you can autofit rows or columns with XlsFile.AutoFitRow, XlsFile.AutoFitCol and XlsFile.AutoFitWorkbook methods. On reports, the new tags &lt;#Row Height> and &lt;#Column Width> allow to change the row height / column width in a report, and to hide, show or autofit columns and rows. See the new Autofitting demo on the reports section.



## New in v 5.1.2.0 - July 2012


- **Small bug fixes.** Stability fixes.



## New in v 5.1.0.0 - May 2012


- **Many important bug fixes and improvements.** For FlexCel 5.1 we focused in polishing every bit of the code, porting thousands of tests and making sure every one was passing, optimizing the code and making it faster, and we even managed to make the executables 700 kb smaller. 5.1 is a very important release and very recommended update from 5.0.5

- **APIMate.** ApiMate for Delphi/C++ Builder is a tool that can open any existing xls/x file, and show you the Delphi or C++ code needed to create that file with FlexCel. It is a very helpful tool for learning the FlexCel API.

- **Improved virtual mode.** Virtual mode now can skip sheets you don't need to read, and also stop reading the file as soon as you have read all the values you need. Look at the improved "Virtual Mode" demo for more information.

- **New demos.** Many new API demos.



## New in v 5.0.5.0 - March 2012


- **Recalculation.** Now FlexCel can natively recalculate the files, with support of over 200 functions.

- **Bug fixes.** Many bug fixes and added support for TXlsxAdapter component for using FlexCel 5 from FlexCel 3. TXlsxAdapter allows you to use a v3 FlexCelGrid with recalculation and xlsx support.



## New in v 5.0.2.0


- **C++ Builder XE2 support.** Now you can use FlexCel from C++ Builder XE2.

- **Integrated help.** Now we include integrated reference for all classes and methods, that you can access by pressing F1 inside RAD Studio.

- **Bug fixes.** Small bug fixes and added support for TAdvGridExcelExport and TAdvGridExcelImport.



## New in v 5.0.0.0 - December 2011


- **First release with the new code base.** FlexCel 5 has been completely rewritten based in the code for FlexCel .NET. There are too many changes to mention, but among them we have Xlsx file support, new reporting engine, pdf export, html export, FireMonkey support, etc.


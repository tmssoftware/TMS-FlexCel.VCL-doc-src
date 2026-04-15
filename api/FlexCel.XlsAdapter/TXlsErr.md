---
uid: TXlsErr
description: TXlsErr
---

# TXlsErr Enumeration

Error Codes\. We use this and not actual strings to make sure all are correctly spelled\.


## Syntax

**Unit:** [FlexCel.XlsAdapter](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ErrInternal|0|Internal|
|ErrTooManyEntries|1|TooManyEntries|
|ErrInvalidContinue|2|InvalidContinue|
|ErrWrongExcelRecord|3|WrongExcelRecord|
|ErrExcelInvalid|4|ExcelInvalid|
|ErrFileIsPasswordProtected|5|FileIsPasswordProtected|
|ErrNotSupportedOnCE|6|NotSupportedOnCE|
|ErrFileIsNotXLS|7|FileIsNotXLS|
|ErrBadFormula|8|BadFormula|
|ErrBadName|9|BadName|
|ErrBadToken|10|BadToken|
|ErrWrongType|11|WrongType|
|ErrInvalidStream|12|InvalidStream|
|ErrEofReached|13|EofReached|
|ErrReadingRecord|14|ReadingRecord|
|ErrInvalidStringRecord|15|InvalidStringRecord|
|ErrInvalidVersion|16|InvalidVersion|
|ErrDupRow|17|DupRow|
|ErrRowMissing|18|RowMissing|
|ErrEscherNotLoaded|19|EscherNotLoaded|
|ErrLoadingEscher|20|LoadingEscher|
|ErrBStoreDuplicated|21|BStoreDuplicated|
|ErrDgDuplicated|22|DgDuplicated|
|ErrDggDuplicated|23|DggDuplicated|
|ErrSolverDuplicated|24|SolverDuplicated|
|ErrChangingEscher|25|ChangingEscher|
|ErrNotImplemented|26|NotImplemented|
|ErrCantCopyPictFmla|27|CantCopyPictFmla|
|ErrBadChartFormula|28|BadChartFormula|
|ErrSectionNotLoaded|29|SectionNotLoaded|
|ErrInvalidDrawing|30|InvalidDrawing|
|ErrXlsIndexOutBounds|31|XlsIndexOutBounds|
|ErrBadCF|32|BadCF|
|ErrInvalidCF|33|InvalidCF|
|ErrInvalidSheetNo|34|InvalidSheetNo|
|ErrDuplicatedSheetName|35|DuplicatedSheetName|
|ErrTooManyPageBreaks|36|TooManyPageBreaks|
|ErrInvalidRow|37|InvalidRow|
|ErrInvalidCol|38|InvalidCol|
|ErrBadRowCount|39|BadRowCount|
|ErrShrFmlaNotFound|40|ShrFmlaNotFound|
|ErrHiddenSheetSelected|41|HiddenSheetSelected|
|ErrNoSheetVisible|42|NoSheetVisible|
|ErrBadCopyRows|43|BadCopyRows|
|ErrBadCopyCols|44|BadCopyCols|
|ErrBadMoveCall|45|BadMoveCall|
|BaseSheetName|46|eSheetName|
|ErrCantDeleteSheetWithMacros|47|CantDeleteSheetWithMacros|
|ErrCantRenameSheetCodenameWithMacros|48|ErrCantRenameSheetCodenameWithMacros|
|ErrTooManyRows|49|TooManyRows|
|ErrTooManyColumns|50|TooManyColumns|
|ErrTooManySheets|51|Trying to insert more than 65536 sheets\.|
|ErrInvalidPassword|52|Invalid password\.|
|ErrPasswordTooLong|53|Password too long\.|
|ErrNotSupportedEncryption|54|Encryption method is not supported\.|
|ErrInvalidNameForARange|55|The name for a named range is invalid\. It should have no more than 255 characters, must no start with a number, and must not contain some special characters\.|
|ErrNameAlreadyExistsAtDifferentIndex|56|The name already exists at a different position in the file\.|
|ErrNameCantBeNamedSameAsATable|57|The name can't be the same of one existing Excel\-Table\.|
|ErrObjectNotFound|58|Could not find the object path inside the shape\.|
|ErrInvalidArrayElement|59|The array element is not any of the supported types\.|
|ErrPxlIsInvalid|60|The Pocket Excel file \(Pxl\) is not on a format FlexCel can understand\.|
|ErrPxlIsInvalidToken|61|The Pocket Excel file \(Pxl\) is not on a format FlexCel can understand\. Token invalid\.|
|ErrStringTooLong|62|The string is longer than the maximum allowed by Excel\.|
|ErrStringEmpty|63|The string can't be empty\.|
|ErrHeaderFooterStringTooLong|64|The string for a header or footer is longer than the maximum allowed by Excel\.|
|ErrFileIsNotSupported|65|The file is not on any on the formats supported by FlexCel \(Excel 2 or newer, Pxl\)\.|
|ErrPxlDoesNotHaveExternalFormulas|66|Pocket Excel does not have support for formulas that reference external files\.|
|ErrInvalidPropertySector|67|Cannot read the properties of this file\.|
|ErrInvalidChart|68|Chart is invalid\.|
|ErrMoveRangesCanNotIntersect|69|Ranges in move calls cannot intersect\.<br />|
|ErrCantMovePartOfTable|70|Can't move a part of a table\.<br />|
|ErrCantMovePartOfArrayFormula|71|Can't move a part of an Array formula\.<br />|
|ErrMoveRangeOutsideBounds|72|Trying to move a range outside bounds\.<br />|
|ErrTooManyCFRules|73|Too many Conditional format rules\.<br />|
|ErrTooManyXFDefs|74|Too many format definitions\.<br />|
|ErrDataValidationFmla1TooLong|75|First formula of Data validation has more than 255 characters\.<br />|
|ErrDataValidationFmla2TooLong|76|Second Formula of Data validation has more than 255 characters\.<br />|
|ErrDataValidationFmla1Null|77|First formula of Data validation is null\.<br />|
|ErrDataValidationFmla2Null|78|Second formula of Data validation is null\.<br />|
|ErrInvalidHyperLink|79|Invalid Hyperlink\.<br />|
|ErrInvalidHyperLinkType|80|Invalid type of Hyperlink\.<br />|
|ErrInvalidFormatStringLength|81|Maximum length for a format string is 255 characters\.<br />|
|ErrInvalidFormatId|82|Too many custom numeric formats\.<br />|
|ErrStreamNeedsReadAccess|83|In order to save as xlsx, the stream needs to have read access besides write\.<br />|
|ErrFileSize0|84|The file we are trying to open has zero size\.<br />|
|ErrStreamAtEnd|85|Stream is at the end\.<br />|
|ErrNullGradient|86|If you specify a gradient pattern, then gradient definition can't be null|
|ErrRangeMustHaveSameSheet|87|Both sheets in the range must be the same|
|ErrMissingPart|88|There is a part missing from the xlsx file\.<br />|
|ErrMalformedXml|89|File has malformed xml, and we can't read it\.<br />|
|SheetAlreadyProcessed|90|Sheet has already been processed\.<br />|
|RecoveryInvalidName|91|A corrupt file has an invalid name\.<br />|
|RecoveryInvalidFmla|92|A corrupt file has an invalid formula\.<br />|
|RecoveryInvalidFormat|93|A corrupt file has an invalid format\.<br />|
|ErrCustomPropIdRepeated|94|The id is repeated\.<br />|
|ErrCustomPropIdInvalid|95|The id is invalid\.<br />|
|TableHeadersMustBeStrings|96|The headers in a table must be strings\.<br />|
|TableHeadersMustBeUnique|97|Table headers must be unique\.<br />|
|TableNameInvalid|98|The name of the table is not valid\.<br />|
|TableColumnsDontMatchRange|99|The number of columns in the column definitions is different from the number of columns in the table range\.<br />|
|TablesMustHaveAtLeastOneRow|100|A table must have at least one row\.<br />|
|DeletingTooManySheets|101|Deleting more sheets than the sheets in the file\.<br />|
|ErrInvalidChartOptions|102|The chart options are of the wrong type\.<br />|
|ErrCantChangeAPieToDoughnut|103|Can't change a pie chart into a doughnut chart\.<br />|
|ErrCantChangeADoughnutToPie|104|Can't change a doughnut chart into a pie chart\.<br />|
|ErrInvalidNegativeAxisId|105|Axis id must be positive\.<br />|
|ErrInvalidAxisId|106|The axis id is too big\.<br />|
|ErrInvalidCodeNameStart|107|Codenames should start with a letter\.<br />|
|ErrInvalidCodeNameChar|108|Codenames should be ASCII\.<br />|
|ErrInvalidCodeNameLen|109|CodeNames must be less than 32 characters\.<br />|
|SeriesIsntBubble|110|Series must be a bubble series\.<br />|
|ErrTooManySeries|111|Trying to insert more than 255 series in a chart\.|
|ErrCantAddTrendLineToChart|112|The type of chart doesn't allow a trendline\.|
|ErrThisOverloadDoesntSupportArrays|113|This version of the method doesn't support array formulas\.|



---
uid: TFlxErr
description: TFlxErr
---

# TFlxErr Enumeration

Error Codes used in Exceptions\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|ErrInternal|0|Unexpected error|
|ErrInvalidCellValue|1|Can't convert the object into a valid value\.|
|ErrNotConnected|2|Adapter's "Connect" Method has not been called\.<br />|
|ErrInvalidRow|3|Trying to access to an invalid row\.<br />|
|ErrInvalidColumn|4|Trying to access to an invalid column\.<br />|
|ErrInvalidValue|5|Generic out of range error\. Params for this message should be taken from TFlxParam\.<br />|
|ErrInvalidValue2|6|Generic out of range error when there are no objects to index\.<br />|
|ErrInvalidValue3|7|Generic out of range error when the specific value is invalid\.<br />|
|ErrDataSetNotFound|8|Can't find a dataset for a named range\.<br />|
|ErrInvalidSheet|9|Sheet name does not exist\.<br />|
|ErrFormulaTooLong|10|Formula is longer than 0xFFFF|
|ErrNotAString|11|When parsing a formula and expecting a string\.<br />|
|ErrUnterminatedString|12|A string missing the ending "|
|ErrUnexpectedId|13|A formula with an invalid identifier\.<br />|
|ErrUnexpectedChar|14|A formula with an invalid character\.<br />|
|ErrInvalidTable|15|A table doesn't exist inside a formula\.<br />|
|ErrTableNotFound|16|Table doesn't exist\.<br />|
|ErrMissingParen|17|A missing parenthesis\.<br />|
|ErrMissingSquareBracket|18|A missing square bracket\.<br />|
|ErrInvalidNumberOfParams|19|Invalid number of parameters for the function\.<br />|
|ErrUnexpectedEof|20|Unexpected end of formula\.<br />|
|ErrFormulaStart|21|Formula must start with "="|
|ErrFormulaInvalid|22|Formula is invalid\.<br />|
|ErrFilterInvalid|23|Filter is invalid\.<br />|
|ErrFunctionNotFound|24|Function on the formula does not exist\.<br />|
|ErrCircularReference|25|A formula refers to itself\.<br />|
|ErrInvalidRef|26|An invalid cell reference\. A valid one is "A1"|
|ErrInvalidRef2|27|An invalid cell reference\. If it is trying to add a reference to an external name, it might be missing a workspace\.<br />|
|ErrInvalidRange|28|An invalid range reference\. A valid one is "A1:A2"|
|ErrInvalidRangeRef|29|The name defining band "\{0\}" has a negative number of rows or columns\. Verify it has absolute references \($A$1:$B$2\) instead of relative \($A$1:B2\)|
|ErrMissingEOT|30|An invalid End of tag \(for example, \<\#\.\.\.>>\)|
|ErrMissingArgs|31|Missing arguments for a function\.<br />|
|ErrTooMuchArgs|32|Too much arguments on a function\.<br />|
|ErrArgsMustBeEven|33|The number of arguments must be multiple of 2\.<br />|
|ErrReadAfterEOF|34|Reading after the end of a datatable\.<br />|
|ErrReadBeforeBOF|35|Reading before the beginning of a datatable\.<br />|
|ErrIntersectingRanges|36|2 data ranges intersect on a report\.<br />|
|ErrEqualRanges|37|2 data ranges are the same, and FlexCel can't figure out which one is the master and which one the detail\.<br />|
|ErrUndefinedFunction|38|Function is not defined on file FunctionNames\.resx|
|ErrUndefinedId|39|Id is not defined on file xxxx|
|ErrInvalidFormat|40|Invalid format on report\.<br />|
|ErrFormatAlreadyExists|41|Format was already defined in the config sheet\.<br />|
|ErrExpressionAlreadyExists|42|Expression was already defined in the config sheet\.<br />|
|ErrColumNotFound|43|Column does not exits\.<br />|
|ErrPropertyNotFound|44|The property does not exist\.<br />|
|ErrMemberNotFound|45|Dataset does not have a field\.<br />|
|ErrDataSetNotInRange|46|Dataset is not inside any named range\.<br />|
|ErrInvalidImage|47|Image is invalid\.<br />|
|ErrCreatingImage|48|Error trying to create an empty image\. Probably out of memory\.<br />|
|ErrOnIncludeReport|49|Error in an included report\.<br />|
|ErrTooManyNestedIncludes|50|Too many nested includes, probably one file is recursively including itself\.<br />|
|ErrTooManyNestedObjects|51|Too many nested objects\.<br />|
|ErrCantFindNamedRange|52|Cannot find the included named range\.<br />|
|ErrUnknownRangeType|53|Range is not \_\_, \_, I\_ or II\_|
|ErrNotSupportedOnTrial|54|This feature is not supported on non commercial version of FlexCel\.<br />|
|ErrUndefinedUserFunction|55|User defined function implementation is null\.<br />|
|ErrUndefinedUserFormat|56|User defined format implementation is null\.<br />|
|ErrDataSetNotFoundInConfig|57|Can't find a dataset for a configsheet\.<br />|
|ErrDataSetNotFoundInExpression|58|Can't find a dataset for an expression on the sheet\.<br />|
|ErrCantChangeRecalcMode|59|RecalcMode can only be changed when no file is open\.<br />|
|ErrWorkbookNull|60|Workbook can't be null on this version of the method\.<br />|
|ErrCompression|61|Error with the compression engine\.<br />|
|ErrInvalidRelationshipNullValues|62|A relationship is invalid\.<br />|
|ErrInvalidRelationship2Tables|63|A relationship is invalid\.<br />|
|ErrInvalidRelationshipFields|64|A relationship is invalid\.<br />|
|ErrInvalidRelationshipDatasetNull|65|A relationship is invalid\.<br />|
|ErrInvalidManualRelationshipDatasetNull|66|A relationship is invalid\.<br />|
|ErrInvalidManualRelationshipFieldCount|67|A relationship is invalid\.<br />|
|ErrInvalidRelationship2Fields|68|A relationship is invalid\.<br />|
|ErrInvalidSql2Params|69|SQL function should have only 2 parameters\.<br />|
|ErrInvalidSplit2Params|70|SPLIT function should have only 2 parameters\.<br />|
|ErrInvalidSplitCount|71|Second parameter of a split function must be a positive integer\.<br />|
|ErrInvalidTop2Params|72|TOP function should have only 2 parameters\.<br />|
|ErrInvalidTopCount|73|Second parameter of a TOP function must be a positive integer\.<br />|
|ErrInvalidMin23Params|74|ATLEAST function should have 2, 3 or 4 parameters\.<br />|
|ErrInvalidMinCount|75|Second parameter of an ATLEAST function must be a positive integer\.<br />|
|ErrInvalidMultipleOf|76|Fourth parameter of an ATLEAST function must be a positive integer\.<br />|
|ErrInvalidNRows1Param|77|ROWS function should have only 1 parameter\.<br />|
|ErrInvalidNRowsCount|78|Parameter of a ROWS function must be a positive integer\.<br />|
|ErrInvalidColumns1Param|79|COLUMNS function should have only 1 parameter\.<br />|
|ErrInvalidJoinTableCount|80|JOIN function should have at least 2 parameters\.<br />|
|ErrInvalidUnionTableCount|81|UNION function should have at least 2 parameters\.<br />|
|ErrInvalidSqlParen|82|Missing closing parenthesis\.<br />|
|ErrInvalidSplitParen|83|Missing closing parenthesis\.<br />|
|ErrInvalidTopParen|84|Missing closing parenthesis\.<br />|
|ErrInvalidAtLeastParen|85|Missing closing parenthesis\.<br />|
|ErrInvalidNRowsParen|86|Missing closing parenthesis\.<br />|
|ErrInvalidColumnsParen|87|Missing closing parenthesis\.<br />|
|ErrInvalidJoinParen|88|Missing closing parenthesis\.<br />|
|ErrInvalidUnionParen|89|Missing closing parenthesis\.<br />|
|ErrInvalidUserTableParen|90|Missing closing parenthesis\.<br />|
|ErrInvalidSqlAdapterNotFound|91|Adapter not found\.<br />|
|ErrInvalidSqlAdapterNoSelect|92|The adapter has not SQL select command defined\.<br />|
|ErrInvalidSqlString|93|SQL string contains invalid characters\.<br />|
|ErrDataSetNull|94|DataSet should not be null\.<br />|
|ErrAdapterNull|95|Adapter should not be null\.<br />|
|ErrSQLCommandNull|96|SQL command should not be null\.<br />|
|ErrInvalidFilterParen|97|Missing parenthesis\.<br />|
|ErrOnConfigTables|98|Error reading config tables\.<br />|
|ErrInvalidDistinctParams|99|Parameters for distinct filter should not be null\.<br />|
|ErrInvalidSqlParams|100|Parameters for SQL parameters should not be null\.<br />|
|ErrSqlParameterNotFound|101|The parameter for a direct sql query was not found\.<br />|
|ErrEofReached|102|EofReached|
|ErrArrayNotSquared|103|All rows on an array must have the same number of columns\.|
|ErrInvalidCols|104|The columns on an array must be between 1 and 256|
|ErrInvalidRows|105|The rows on an array must be between 1 and 65536|
|ErrInvalidErrorCode|106|Invalid error code|
|ErrEmptyFolder|107|The folder does not contain any file of the needed type\.|
|ErrPDFFontFolderDoesntExist|108|The folder for fonts doesn't exist\.|
|ErrNotASinglePDFFontFolderExists|109|None of the folders for fonts exist\.<br />|
|ErrTiffEncoderNotFound|110|Cannot find a Tiff Encoder\.|
|ErrInvalidImageFormat|111|Invalid image format\.|
|ErrInvalidHtmlParam|112|Invalid parameter for html tag\.|
|ErrInvalidRowColParameters|113|Invalid parameter for rowheight or columnwidth tag\.|
|ErrInvalidRowColParameters2|114|Invalid second parameter for rowheight or columnwidth tag\.|
|ErrInvalidRowColParameters3|115|Invalid third parameter for rowheight or columnwidth tag\.|
|ErrInvalidRowColParameters4|116|Invalid fourth parameter for rowheight or columnwidth tag\.|
|ErrInvalidRefTag|117|Invalid parameter for ref tag, 1 parameter version\.|
|ErrInvalidRefTag2|118|Invalid parameter for ref tag, 2 parameter version\.|
|ErrInvalidRefTag3|119|Invalid parameter for ref tag, 3 parameter version\.|
|ErrInvalidGlobalAdjustment|120|Invalid parameter on Autofit settings tag\.<br />|
|ErrInvalidGlobalAdjustmentFixed|121|Invalid parameter on Autofit settings tag\.<br />|
|ErrInvalidGlobalAutofit|122|Invalid adjustment on Autofit settings tag\.<br />|
|ErrInvalidAutoFitMerged|123|Invalid Merge mode\.<br />|
|ErrSplitNeedsOneAndOnlyOneDetail|124|When using Splitted tables, the detail must directly follow the master\.<br />|
|ErrSplitNeedsOnlyOneMaster|125|A table cannot be assigned to 2 different splits masters\.<br />|
|ErrUserTableEventNotAssigned|126|The template has User table tags, but there is no UserTable event assigned to the report\.<br />|
|ErrTableDoesNotSupportFilter|127|This is a virtual table, and it didn't define the methods needed to filter it\.<br />|
|ErrTableDoesNotSupportTag|128|This is a virtual table, and it didn't define the methods needed to support this tag\.<br />|
|ErrTableDoesNotSupportTagConfig|129|This is a virtual table, and it didn't define the methods needed to support this tag\.<br />|
|ErrTableDoesNotSupportMasterDetail|130|This is a virtual table, and it didn't define the methods needed to support master detail relationships\.<br />|
|ErrTableDoesNotSupportLookup|131|This is a virtual table, and it didn't define the methods needed to be used as a Lookpup source\.<br />|
|ErrInvalidEncodingForMIME|132|The encoding con not be used to create a MIME file\.<br />|
|ErrBeginExportNotCalled|133|Before exporting a sheet you need to call BeginExport|
|ErrBeginPrintNotCalled|134|Before printing a sheet you need to call BeginPrint|
|ErrNoDuplicatedPreprocess|135|A preprocess tag must not be nested\.<br />|
|ErrInvalidDefinedGlobal|136|If the Defined tag has 2 parameters, the second must be GLOBAL or LOCAL\.<br />|
|ErrInvalidRowColDelete|137|Invalid parameters for delete row/col|
|ErrNeedsUnmanaged|138|The operation needs unmanaged permissions in order to complete\.<br />|
|ErrInvalidApplyTag|139|A format definition in the config sheet is not valid\.<br />|
|ErrAtCell|140|Error at cell n\.<br />|
|CellError|141|Message that will be written in a cell when there is an error in a report and [TFlexCelReport.ErrorsInResultFile](../FlexCel.Report/TFlexCelReport/ErrorsInResultFile.md) is true\.<br />|
|ErrInvalidIncludeStatic|142|Invalid parameter for include\.<br />|
|ErrInvalidIncludeRowCol|143|Invalid parameter for include\.<br />|
|ErrInvalidAutoPageBreaksPercent|144|Invalid value in the percent of page used in an automatic page break tag\.<br />|
|ErrInvalidAutoPageBreaksPageScale|145|Invalid PageScale in automatic page break tag\.<br />|
|ErrInvalidImgPosParameter|146|Invalid parameter for a ImgPos tag\.<br />|
|ErrInvalidImgFitParameter|147|Invalid parameter for a ImgFit tag\.<br />|
|ErrDuplicatedLinkedFile|148|Trying to add an xls file that already exists to a Workspace collection\.<br />|
|ErrInvalidAggParameter|149|Aggregate must be "SUM", "COUNT", "AVG", "MAX" or "MIN"|
|ErrAggFilterMustReturnABooleanValue|150|An agreggate filter must return a boolean value\.<br />|
|ErrFilterMustReturnABooleanValue|151|A filter must return a boolean value\.<br />|
|ErrFontNotFound|152|Font was not found in the system\.<br />|
|ErrGlyphNotFound|153|Font doesn't contain the character\.<br />|
|ErrUsedFallbackFont|154|Font is missing a character and a fallback font was used instead\.<br />|
|ErrFauxBoldOrItalic|155|Font doesn't have italic or bold variant\.<br />|
|ErrFontNotSupported|156|Font is not supported\.<br />|
|ErrInvalidEmptyName|157|Name cannot be empty\.<br />|
|ErrNameTooLong|158|Name is too long\.<br />|
|ErrStyleDoesntExists|159|Named style doesn't exists\.<br />|
|ErrStyleAlreadyExists|160|Style already exists\.<br />|
|ErrCantRenameBuiltInStyle|161|Built\-in styles can't be renamed\.<br />|
|ErrCantDeleteBuiltInStyle|162|Built\-in styles can't be deleted\.<br />|
|ErrCantAddStyleFormats|163|Style formats have to be added using SetStyle method, not with addformat\.<br />|
|ErrCantMixCellAndStyleFormats|164|You can't replace a cell format with a style format or viceversa\.<br />|
|ErrInvalidColorType|165|ColorType is of the wrong type\.<br />|
|ErrInvalidColorValue|166|Value for the color is outside bounds\.<br />|
|ErrInvalidColorEnum|167|Value must be one of the enum, and can't be none\.<br />|
|ErrStringConstantInFormulaTooLong|168|String constant in formula is too long\. \(max 255 chars\)|
|ErrNoBorderColorSet|169|When you set a border style different from none, then the border color must be set too\.<br />|
|ErrCantUseThemeColorsInsideATheme|170|You can use a themed color to define a color inside a theme\.<br />|
|ErrNullParameter|171|Parameter can't be null\.<br />|
|ErrNullOrEmptyParameter|172|Parameter can't be null or empty\.<br />|
|ErrRangeNameAlreadyExists|173|The name for the range already exists\.<br />|
|ErrInvalidName|174|Name is invalid\.<br />|
|ErrInvalidEnum|175|Enum must exist\.<br />|
|ErrInvalidLinQDetail|176|Detail table doesn't have a parent\.<br />|
|ErrInvalidSortString|177|The sort string is not supported\.<br />|
|ErrEmptyKeyNames|178|The keys in a lookup can't be empty\.<br />|
|ErrValuesAndKeysMismatch|179|Keys and values in a lookup must have the same number of elements\.<br />|
|ErrDatasetDoesntSupportWhere|180|When using LINQ, FlexCel implements filters by calling a "Where\(string\)" method in the data table\. If the table doesn't have a "Where\(string\)" method, FlexCel can't filter the records\.<br />|
|ErrInvalidReportRowCount|181|The count of records in a table is different from the actual number of records when reading the data\. This means that  someone else has inserted or deleted records while this report was running\. To avoid this issue, make sure you run the report with isolation level = SNAPSHOT\.<br />|
|ErrInvalidFilterDateTime|182|Dates in filters must be written as "yyy\-dd\-mm hh:mm:ss"|
|ErrInvalidXlsxFile|183|Invalid xlsx file\.<br />|
|ErrInvalidContentType|184|File doesn't have a valid content\-type|
|ErrInvalidZip|185|Invalid zip file\.<br />|
|ErrCompressionNotSupported|186|Compression mode not supported\.<br />|
|ErrReadingOutOfBounds|187|Trying to read after the end of the stream\.<br />|
|ErrInvalidLocalHeader|188|Invalid local header in the zip file\.<br />|
|ErrZipNameTooLong|189|File name is too long\.<br />|
|ErrInvalidIndex|190|Invalid Index\.<br />|
|ErrCantRead|191|Can't read from a compression stream\.<br />|
|ErrCantSeek|192|Can't seek in a compression stream\.<br />|
|ErrMustSpecifyFolder|193|You must specify a folder to compress\.<br />|
|ErrValueIsNotOfType|194|Value is not of the expected type\.<br />|
|ErrNoPagesToPrint|195|There are no pages to print\.<br />|
|ErrFontNotLicensed|196|The font licensing doesn't allow embedding\.<br />|
|ErrFormatConditionCantBeNull|197|The format condition can't be null\.<br />|
|ErrInvalidTypeForShapeOption|198|The shape option is a wrong type\.<br />|
|InvalidShapeGeomXML|199|The XML defining a shapegeom must start with shapeGeom\.<br />|
|InvalidShapeGeomXML2|200|The XML defining a shapegeom must follow shapeGeom with custGeom or prstGeom\.<br />|
|ErrStructRefNoColumn|201|The column referenced in the structured reference can't be found\.<br />|
|ErrEmptyTableStyleName|202|The name of a table style can't be empty\.<br />|
|ErrTableStyleDoesntExist|203|The table style name does not exist\.<br />|
|ErrTableStyleAlreadyExists|204|The table style name already exists\.<br />|
|ErrCantSaveStrictXlsm|205|Strict xlsx files don't support macros\.<br />|
|ErrReportTableNeedsTwoRows|206|Tables used as datasources of a report need at least 2 rows\.<br />|
|ErrEmptyStack|207|The stack is empty and it is not possible to pop an element\.<br />|
|ErrEmptyArrayMember|208|Arrays in formulas can't have empty elements\.<br />|
|ErrInvalidArrayMember|209|Invalid element in a formula array\.<br />|
|ErrCantInsertAChartInANotWorksheet|210|Charts can only be inserted in normal sheets\.<br />|
|ErrInvalidLambdaParameterName|211|Lambda parameter names can't start with a number, or be a valid cell reference, etc\.<br />|
|ErrRepeatedLambdaParameter|212|You can't define the same parameter twice in a Lambda expression or a LET function\.<br />|
|MustHaveAtLeastOneWindow|213|A workbook must have at least one window\.<br />|
|ErrRequiredLambdaParameterAfterOptional|214|A required lambda parameter cannot come after an optional one\.<br />|
|ErrInvalid3DRef|215|Invalid 3D reference\.<br />|
|ErrInvalidSheetVisibleParameters|216|Invalid parameter for sheet visible tag\.|
|ErrFontInvalid|217|The font has invalid height or width\.|
|ErrInvalidGroupParamCount|218|You need to group at least two shapes\.|



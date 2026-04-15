---
uid: TFlexCelReport
description: TFlexCelReport
---

# TFlexCelReport Class

Component for creating reports on Excel based on a template\. It will read an xls file, replace tags with data read from a database or memory, and save a new file with the data\.


## Syntax

**Unit:** [FlexCel.Report](../index.md)

<pre><code class="lang-delphi hljs">TFlexCelReport = class(TFlexCelObject, IDataTableFinder);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tflexcelreportcreate)<br />  [Create\(Boolean\)](Create.md#tflexcelreportcreateboolean)<br />  [Create\(Integer, string, TDataSourceInfoList, TFlexCelReport\)](Create.md#tflexcelreportcreateinteger-string-tdatasourceinfolist-tflexcelreport)<br />|


## Methods

|Name|Description|
|---|---|
|[OnBeforeReadTemplate](OnBeforeReadTemplate.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [BeforeReadTemplate](BeforeReadTemplate.md)|
|[OnBeforeGenerate&#8203;Workbook](OnBeforeGenerateWorkbook.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [BeforeGenerate&#8203;Workbook](BeforeGenerateWorkbook.md)|
|[OnAfterGenerate&#8203;Workbook](OnAfterGenerateWorkbook.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [AfterGenerate&#8203;Workbook](AfterGenerateWorkbook.md)|
|[OnBeforeGenerate&#8203;Sheet](OnBeforeGenerateSheet.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [BeforeGenerateSheet](BeforeGenerateSheet.md)|
|[OnAfterGenerateSheet](OnAfterGenerateSheet.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [AfterGenerateSheet](AfterGenerateSheet.md)|
|[OnGetImageData](OnGetImageData.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [GetImageData](GetImageData.md)|
|[OnCustomizeChart](OnCustomizeChart.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [CustomizeChart](CustomizeChart.md)|
|[OnGetInclude](OnGetInclude.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [GetInclude](GetInclude.md)|
|[OnUserTable](OnUserTable.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [UserTable](UserTable.md)|
|[OnLoadTable](OnLoadTable.md)|Replace this event when creating a custom descendant of FlexCelReport\. See also [LoadTable](LoadTable.md)|
|[PreLoad](PreLoad.md)|Used on included reports\. For performance, the report will be parsed only once\.<br />|
|[ResolveString](ResolveString.md)|This is the method that does the parsing\. Could be made virtual and override it on a descendant class to support  self defined Tags\.<br />|
|[Unload](Unload.md)|This cleans the resources allocated by preload\.<br />|
|[Run](Run.md)|**Overloaded<br />**  [Run\(TExcelFile\)](Run.md#tflexcelreportruntexcelfile)<br />  [Run\(string, string\)](Run.md#tflexcelreportrunstring-string)<br />  [Run\(TStream, TStream\)](Run.md#tflexcelreportruntstream-tstream)<br />  [Run\(TStream, TStream, TFileFormats\)](Run.md#tflexcelreportruntstream-tstream-tfileformats)<br />|
|[Cancel](Cancel.md)|Cancels a running report\. This method is equivalent to setting [Canceled](Canceled.md) = true\.<br />|
|[AddTable](AddTable.md)|**Overloaded<br />**  [AddTable\(string, TArray\<T>\)](AddTable.md#tflexcelreportaddtablestring-tarrayt)<br />  [AddTable\(string, TVirtualDataTable\)](AddTable.md#tflexcelreportaddtablestring-tvirtualdatatable)<br />  [AddTable\(string, TList\<T>, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tlistt-tdisposemode)<br />  [AddTable\(TDataModule, TRecordCountMode, TDisposeMode\)](AddTable.md#tflexcelreportaddtabletdatamodule-trecordcountmode-tdisposemode)<br />  [AddTable\(string, TVirtualDataTable, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tvirtualdatatable-tdisposemode)<br />  [AddTable\(string, TDataSet, TRecordCountMode, TDisposeMode\)](AddTable.md#tflexcelreportaddtablestring-tdataset-trecordcountmode-tdisposemode)<br />|
|[ClearTables](ClearTables.md)|Clear the collection of tables available to the report\.<br />|
|[GetTable](GetTable.md)|Returns the VirtualDataTable with the specified name that was added to the report\.<br />|
|[AddConnection](AddConnection.md)|Adds an adapter to use from the template on the DIRECT SQL commands\.<br />**For security reasons, make sure this adapter ONLY GRANTS READONLY ACCESS TO THE DATA**|
|[ClearConnections](ClearConnections.md)|Clear the collection of connections available to the report\.<br />|
|[AddSqlParameter](AddSqlParameter.md)|Adds an SQL parameter to use from the template on the DIRECT SQL commands\.<br />Note that the parameter must have a name even if you are using positional parameters \("?"\) because on the template you should always write named parameters\.<br />|
|[ClearParameters](ClearParameters.md)|Clear the collection of SQL parameters available to the report\.<br />|
|[SetValue](SetValue.md)|Sets a variable for the report\.<br />|
|[ClearValues](ClearValues.md)|Destroys all variables on the report\. To add new variables, use [SetValue](SetValue.md)|
|[SetExpression](SetExpression.md)|Sets a user\-defined expression to be used in the report\. Different from [SetValue](SetValue.md) this method will evaluate the \<\#tags> in "value"\. This allows you to provide formula functionality to end users, and to reuse the same report for  different formulas\.<br />|
|[ClearExpressions](ClearExpressions.md)|Destroys all user\-defined expressions on the report\. To add new expressions, use [SetExpression](SetExpression.md)|
|[SetUserFunction](SetUserFunction.md)|Adds a new user defined function to be used with the report\.<br />The User function object is managed by the report, so you don't have to free it once you used this method to add it to the report\.<br />For information on how to create the user function, see [TFlexCelUserFunction](../TFlexCelUserFunction/index.md)|
|[ClearUserFunctions](ClearUserFunctions.md)|Destroys all user defined functions on the report\. To add new functions, use [SetUserFunction](SetUserFunction.md)|
|[SetUserFormat](SetUserFormat.md)|Adds a new user defined format to be used with the report\.<br />For information on how to create the user format function, see [TFlexCelUserFormat](../TFlexCelUserFormat/index.md)|
|[ClearUserFormats](ClearUserFormats.md)|Destroys all user defined formats on the report\. To add new formats, use [SetUserFormat](SetUserFormat.md)|
|[AddRelationship](AddRelationship.md)|**Overloaded<br />**  [AddRelationship\(string, string, string, string\)](AddRelationship.md#tflexcelreportaddrelationshipstring-string-string-string)<br />  [AddRelationship\(string, string, TArray\<string>, TArray\<string>\)](AddRelationship.md#tflexcelreportaddrelationshipstring-string-tarraystring-tarraystring)<br />|
|[ClearRelationships](ClearRelationships.md)|Clears all relationships added by [AddRelationship\(&#8203;&#8203;string, string, string, string\)](AddRelationship.md#tflexcelreportaddrelationshipstring-string-string-string)\.<br />|


## Properties

|Name|Description|
|---|---|
|[DataConversionEvent](DataConversionEvent.md)|Set this function to return a the value that must be written in the report for an speific type of record, class or array\.<br />|
|[Canceled](Canceled.md)|If true the report has been canceled with [Cancel](Cancel.md) method\.<br />You can't set this variable to false, and setting it true is the same as calling [Cancel](Cancel.md)\.<br />|
|[Progress](Progress.md)|Progress of the report\. This variable must be accessed from other thread\.<br />|
|[DeleteEmptyRanges](DeleteEmptyRanges.md)|This property is obsolete\. Use DeleteEmptyBands instead\. Determines if FlexCel will delete or just clear ranges with empty datasets \(0 records\)\.<br />|
|[DeleteEmptyBands&#8203;Fixed](DeleteEmptyBandsFixed.md)|Determines if FlexCel will delete or just clear ranges with empty datasets \(0 records\), **for FIXED bands**\.<br />Note that normally you don't want Fixed bands to delete rows, so this property defaults to [TDeleteEmpty&#8203;Bands.&#8203;Clear&#8203;Data&#8203;Only](../TDeleteEmptyBands.md)\.<br />|
|[DeleteEmptyBands](DeleteEmptyBands.md)|Determines if FlexCel will delete or just clear ranges with empty datasets \(0 records\)\.<br />Note that this property doesn't apply to FIXED bands, those are controlled with [DeleteEmptyBands&#8203;Fixed](DeleteEmptyBandsFixed.md)|
|[UseExcelTables&#8203;AsBands](UseExcelTablesAsBands.md)|Determines if FlexCel will use Tables named as "\_\_table\_\_" or similar as band definitions\.<br />|
|[RenameExcelTables&#8203;Used&#8203;AsBands](RenameExcelTablesUsedAsBands.md)|Determines if FlexCel will rename Tables used as band definitions after the report is run to remove the extra "\_\_" in the name\.<br />|
|[AllowOverwriting&#8203;Files](AllowOverwritingFiles.md)|Determines if FlexCel will automatically delete existing files or not\.<br />|
|[ResetCellSelections](ResetCellSelections.md)|When true, all sheets will selections will be reset to A1\. This way, you do not need to care about setting the correct selection when editing the template\.<br />|
|[HtmlMode](HtmlMode.md)|When true, FlexCel will interpret the text as HTML, and honor the tags that it can understand\.<br />Note that when in HtmlMode, many consecutive spaces will be interpreted as one, and carriage returns will be interpreted as spaces\. To enter real carriage returns you need to enter a<br />tag \(unless the text is inside \<pre> tags\)\.<br />Also &amp; symbols need to be escaped\. For more info on HTML syntax supported, see [TExcelFile.&#8203;Set&#8203;Cell&#8203;From&#8203;Html\(&#8203;&#8203;Integer, Integer, string, Integer\)](../../FlexCel.Core/TExcelFile/SetCellFromHtml.md#texcelfilesetcellfromhtmlinteger-integer-string-integer)[...[more]](HtmlMode.md)|
|[DisableSQLValidation](DisableSQLValidation.md)|If false \(the default\) FlexCelReport will only allow DirectSQL queries that begin with "SELECT", to avoid people doing inserts or deletes from the config sheet\.<br />If true, FlexCelReport will pass the DirectSQL queries you write in the config sheet directly to the server\.<br />**Caution:** Setting this property to true might have security implications\. Take a look at the remarks\.<br />|
|[EnterFormulas](EnterFormulas.md)|When true, FlexCel will try to enter any string starting with "=" as a formula instead of text\.<br />If this property is true, any string you enter that starts with "=" must be a valid formula, or an error will be raised\.<br />When you know a priori which cells will have formulas, you might want to use the \<\#formula> tag instead\.<br />|
|[TryToConvertStrings](TryToConvertStrings.md)|When true, FlexCel will try to convert strings to numbers or dates before entering them into the cells\.<br />**USE THIS PROPERTY WITH CARE\!**  You shouldn't normally need to use this property, since FlexCel automatically enters numbers or dates in the DataSets as number or dates in the Excel file\. If you need to use this property, it means that data in your database is stored as strings when they should not be\. So the correct fix is to fix the columns you know should have numbers to have numbers, NOT to use this property\. This is just a workaround when you can't do anything else about it\.[...[more]](TryToConvertStrings.md)|
|[ExpressionRecursion&#8203;Limit](ExpressionRecursionLimit.md)|Defines how much nesting you can have in Expressions before FlexCel throws an error\. You might have an expression like \<\#A> which is defined based in another expression \<\#B> which in turn is defined based in another one that finally might come back to \<\#A> As it is not possible for FlexCel to know if the recursion will finish or  loop forever, it will try until it reaches the limit you set here\. Note that a too big limit could cause a stack overflow\.<br />|
|[RecalcMode](RecalcMode.md)|Determines if the report will be recalculated before saving\.<br />See [TExcelFile.&#8203;Recalc&#8203;Mode](../../FlexCel.Core/TExcelFile/RecalcMode.md) for more info\.<br />|
|[RecalcVersion](RecalcVersion.md)|**Before changing this property, look at [TExcelFile.&#8203;Recalc&#8203;Version](../../FlexCel.Core/TExcelFile/RecalcVersion.md)** Determines if the formulas will be recalculated when Excel opens them\.<br />|
|[ErrorActions](ErrorActions.md)|Determines if FlexCel will throw Exceptions or just ignore errors on specific situations\. When the errors are ignored, they will be logged into the [TFlexCelTrace](../../FlexCel.Core/TFlexCelTrace/index.md) class\.<br />|
|[ErrorsInResultFile](ErrorsInResultFile.md)|When true and there is an error reading cells in the template or writing the cells in the report, the error message will be written in the corresponding cell on the generated report\. No Exception will be thrown\.<br /><br />You can use this property to **DEBUG** reports, as it provides an easy way to see all errors at once in the place they are produced\. But is it recommended that you leave this property **FALSE** in production,  or you could create xls files with error messages inside\. See also [DebugExpressions](DebugExpressions.md)|
|[DebugExpressions](DebugExpressions.md)|Set this value to true if you want to analyze how FlexCel is evaluating the tags in a file\. When true, a full stack trace will be written in the cell instead of the tag values\. See ['Debugging reports' in the Reports Designer Guide](xref:ReportsDesignerGuide#debugging-reports) for information on how to use those stack traces\.<br />|
|[DebugIntelligent&#8203;Page&#8203;Breaks](DebugIntelligentPageBreaks.md)|Set this value to true if you want to analyze how FlexCel is setting up the intelligent page breaks\. When this property is true, FlexCel will add one row at the top of the spreadsheet \(if the sheet has keeptogether column ranges\),  and one column at the left of the spreadsheet \(if the sheet has keeptogether row ranges\)\.<br />This row and column will show the levels of keeptogether in the respective column and row\. See ['Debugging intelligent page breaks' in the Reports Designer Guide](xref:ReportsDesignerGuide#debugging-intelligent-page-breaks)[...[more]](DebugIntelligentPageBreaks.md)|
|[SqlParameterReplace](SqlParameterReplace.md)|Format string for replacing the standard parameter names on DIRECT SQL commands\. You can leave it empty for ODBC, OLEDB or SQLSERVER databases\.<br />See Also [SqlParametersType](SqlParametersType.md)|
|[SqlParametersType](SqlParametersType.md)|Type of parameters for the database\. Positional parameters are the ones where you write  "?" on the sql, and positional are when you write a name, like "@employee" or ":orderid"\.<br />See Also [SqlParameterReplace](SqlParameterReplace.md)|
|[SemiAbsolute&#8203;References](SemiAbsoluteReferences.md)|When this property is set to true, absolute references to cells inside bands being copied will be treated as relative\.<br />This way, if you have "=$A$1" inside a band and cell A1 is also inside the band, it will change to A2,A3\.\.etc when the band is copied down\.<br />This can be useful in a master\-detail report, where you want the cells in the detail to point to a fixed cell inside every record of the master\.<br />See [TExcelFile.&#8203;Semi&#8203;Absolute&#8203;References](../../FlexCel.Core/TExcelFile/SemiAbsoluteReferences.md)[...[more]](SemiAbsoluteReferences.md)|


## Events

|Name|Description|
|---|---|
|[BeforeReadTemplate](BeforeReadTemplate.md)|Fires before starting to generate the report and before the template has been loaded\.<br />It allows you to provide the template password if you are using one\.<br />|
|[BeforeGenerate&#8203;Workbook](BeforeGenerateWorkbook.md)|Fires before starting to generate the report but after the template has been loaded\.<br />It allows to do some in\-place modifications to the template before generating the report\.<br />|
|[AfterGenerate&#8203;Workbook](AfterGenerateWorkbook.md)|Fires After the report has been fully generated but is not saved\.<br />Allows to do last clean up things before saving the report\.<br />|
|[BeforeGenerateSheet](BeforeGenerateSheet.md)|Fires Before each sheet on the file is generated\.<br />|
|[AfterGenerateSheet](AfterGenerateSheet.md)|Fires After each sheet on the file is generated\.<br />|
|[GetImageData](GetImageData.md)|Fires before an image is saved to the report\.<br />Use it if the image is on a proprietary format on the database, to return a format FlexCel can understand\.<br />|
|[CustomizeChart](CustomizeChart.md)|Fires for each chart in each sheet, after the report has been generated\.<br />Allows to do custom modifications to the charts, like for example setting series colors\.<br />|
|[GetInclude](GetInclude.md)|Fires before including a file with \<\#include>\.<br />Use it if you want to provide an alternative path for the file, of if you want to read the include file from a different place, for example a database or an embedded resource\.<br />|
|[UserTable](UserTable.md)|Fires on each \<\#USER TABLE> tag in the config sheet, allowing to add your own datasets to the report\.<br />|
|[LoadTable](LoadTable.md)|Fires whenever an undefined table is called, allowing to load your own datasets in demand to the report\. For more control, you might use User Tables\. Look at the example for more information\.<br />|



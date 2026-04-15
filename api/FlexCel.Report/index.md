---
uid: FlexCel.Report
description: FlexCel.Report
---

# FlexCel.Report Namespace

This is the FlexCel reporting engine\. You need to use this unit when using the class TFlexCelReport\.


## Classes

|Name|Description|
|---|---|
|[TCustomizeChart&#8203;Event&#8203;Args](TCustomizeChartEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;Customize&#8203;Chart](TFlexCelReport/CustomizeChart.md)|
|[TFlexCelReport](TFlexCelReport/index.md)|Component for creating reports on Excel based on a template\. It will read an xls file, replace tags with data read from a database or memory, and save a new file with the data\.<br />|
|[TFlexCelReport&#8203;Progress](TFlexCelReportProgress/index.md)|Indicates how much of the report has been generated\.<br />|
|[TFlexCelUserFormat](TFlexCelUserFormat/index.md)|A class used to define a cell format in code, that you can call from a report\.<br />|
|[TFlexCelUserFunction](TFlexCelUserFunction/index.md)|A class used to define a FlexCel user function, that you can call from a report\.<br />|
|[TGenerateEventArgs](TGenerateEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;Before&#8203;Generate&#8203;Workbook](TFlexCelReport/BeforeGenerateWorkbook.md), [TFlexCelReport.&#8203;After&#8203;Generate&#8203;Workbook](TFlexCelReport/AfterGenerateWorkbook.md), [TFlexCelReport.&#8203;Before&#8203;Generate&#8203;Sheet](TFlexCelReport/BeforeGenerateSheet.md) and [TFlexCelReport.&#8203;After&#8203;Generate&#8203;Sheet](TFlexCelReport/AfterGenerateSheet.md)|
|[TGetImageData&#8203;Event&#8203;Args](TGetImageDataEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;Get&#8203;Image&#8203;Data](TFlexCelReport/GetImageData.md)|
|[TGetIncludeEventArgs](TGetIncludeEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;Get&#8203;Include](TFlexCelReport/GetInclude.md)|
|[TLoadTableEventArgs](TLoadTableEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;Load&#8203;Table](TFlexCelReport/LoadTable.md)|
|[TOneCellValue](TOneCellValue/index.md)|A list of TOneSectionValue\. Has a parsed version of what is on a cell\.<br />|
|[TRelation](TRelation/index.md)|A data relation between two tables\. Different from standard \.NET datarelations, this class is not tied to ADO\.NET, and allows you to specify relationships between any arbitrary VirtualDataTable objects\.<br />|
|[TSplitLink](TSplitLink/index.md)|Specifies a "Split" relation between two tables\.<br />|
|[TUserTableEventArgs](TUserTableEventArgs/index.md)|Arguments passed on [TFlexCelReport.&#8203;User&#8203;Table](TFlexCelReport/UserTable.md)|
|[TVirtualDataTable](TVirtualDataTable/index.md)|Base class for a table used on FlexCelReport\.<br />Inherit from this class and [TVirtualData&#8203;Table&#8203;State](TVirtualDataTableState/index.md) to create your custom sources of data\.<br />Make sure you read **['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)** for more information\.<br />|
|[TVirtualData&#8203;Table&#8203;State](TVirtualDataTableState/index.md)|A table that corresponds to a band on the report\.<br />Make sure you read **['Appendix virtual datasets' in the Reports Developer Guide](xref:ReportsDeveloperGuide#appendix-virtual-datasets)** for more information\.<br />|


## Records

|Name|Description|
|---|---|
|[TFlexCelData&#8203;Conversion&#8203;Args](TFlexCelDataConversionArgs/index.md)|Contains the arguments for a TFlexCelData&#8203;Conversion&#8203;Event\.&#8203;<br />|
|[TLookupField&#8203;Definition](TLookupFieldDefinition/index.md)|Encapsulates the data for a lookup tag in a report\.<br />|
|[TMasterDetailLink](TMasterDetailLink/index.md)|A parent table and a parent field used on a master\-detail relationship\.<br />|
|[TReportTag](TReportTag/index.md)|Tags used in reports\.<br />|
|[TReportValue](TReportValue/index.md)|Contains the values you can enter inside a report\. This might be a TCellValue, an array of CellValues or an image as a ByteArray\.<br />|


## Enumerations

|Name|Description|
|---|---|
|[TAggregateType](TAggregateType.md)|Enumeration with the different kind of aggregations that can be done in a FlexCelReport\.<br />|
|[TApplyFormatTagEnum](TApplyFormatTagEnum.md)|Configuration strings used in applying a part of a format\. Internal use\.<br />|
|[TConfigTagEnum](TConfigTagEnum.md)|Configuration strings\. Internal use\.<br />|
|[TDeleteEmptyBands](TDeleteEmptyBands.md)|Defines how bands will be removed when they have 0 records\.<br />|
|[TDisposeMode](TDisposeMode.md)|Indicates if FlexCel must dispose a table after it is done using it\.<br />|
|[TErrorActions](TErrorActions.md)|Enumerates what to do on different FlexCel error situations\.<br />|
|[TFlexCelReport&#8203;Progress&#8203;Phase](TFlexCelReportProgressPhase.md)|Phase of the report we are in\.<br />|
|[TRecordCountMode](TRecordCountMode.md)|Sets the way FlexCel will count the records\.<br />|
|[TSqlParametersType](TSqlParametersType.md)|How the parameters for Direct SQL queries are\.<br />Change it only if your database uses positional parameters and it is not ODBC or OLEDB\.<br />|
|[TValueType](TValueType.md)|All the things we can find on a cell\.<br />|


## Anonymous methods

|Name|Description|
|---|---|
|[TFlexCelData&#8203;Conversion&#8203;Event](TFlexCelDataConversionEvent.md)|A function to convert a class, record or array into a value FlexCel can write in the template\.<br /><br /><br />"v": Value to be converted\.<br /><br /><br />"ConvertedValue": In this variable you need to return the converted value\.<br />|
|[TFlexCelSQLParameter&#8203;Method](TFlexCelSQLParameterMethod.md)|Use this method to assign the SQL parameters in a query\.&#8203;<br />&#8203;"param&#8203;Name"&#8203;: This is the parameter we are setting\. This  name doesn't include the ":" or "@" prefix for the parameter\.<br /><br /><br />"dataset": This is the dataset where you need to assign the parameter\. You will need to cast this value to the specific TDataSet you created in TFlexCelSQLQuery&#8203;Method, and assign the parameter there\.<br />|
|[TFlexCelSQLQuery&#8203;Method](TFlexCelSQLQueryMethod.md)|Use this method to return a dataset where FlexCel can execute the SQL Query\. The type of dataset you return depends on the database you are accessing and the Delphi components you are using to access that database\.<br />|


## Types

|Name|Description|
|---|---|
|[TCustomizeChart&#8203;Event&#8203;Handler](TCustomizeChartEventHandler.md)|Delegate for CustomizeChart event\.<br />|
|[TGenerateEvent&#8203;Handler](TGenerateEventHandler.md)|Generic delegate for After/Before generate events\.<br />|
|[TGetImageData&#8203;Event&#8203;Handler](TGetImageDataEventHandler.md)|Delegate for GetImageData event\.<br />|
|[TGetIncludeEvent&#8203;Handler](TGetIncludeEventHandler.md)|Delegate for GetInclude event\.<br />|
|[TLoadTableEvent&#8203;Handler](TLoadTableEventHandler.md)|Delegate for LoadTable event\.<br />|
|[TUserTableEvent&#8203;Handler](TUserTableEventHandler.md)|Delegate for UserTable event\.<br />|



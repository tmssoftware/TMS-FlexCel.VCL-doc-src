---
uid: TExcelFile.AddUserDefinedFunction
description: TExcelFile.AddUserDefinedFunction
---

# TExcelFile\.AddUserDefinedFunction Method

Adds a custom formula function to the FlexCel recalculation engine\. Note that this formulas are only valid for Excel custom formulas, not for internal ones\.
For example, you could define "EDATE" since it is a custom formula defined in the Analysis Addin, but you cannot redefine "SUM"\.
Note that if a custom formula with the name already exists, it will be replaced\. Names are Case insensitive \("Date" is the same as "DATE"\)\.

Also note that some user defined functions come already built in FlexCel, so you might not need to define them\.
For more information on adding Custom Formulas make sure you read ['Using Excel's user defined functions (UDF)' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf) and take a look at the [Excel User Defined Functions Delphi](xref:Excel_User_Defined_Functions-Delphi) example\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">procedure <a href="../TExcelFile/index.md">TExcelFile</a>.AddUserDefinedFunction(const scope: <a href="../TUserDefinedFunctionScope.md">TUserDefinedFunctionScope</a>; const location: <a href="../TUserDefinedFunctionLocation.md">TUserDefinedFunctionLocation</a>; const userFunction: <a href="../TUserDefinedFunction/index.md">TUserDefinedFunction</a>); virtual; abstract;</code></pre>

## Parameters

|<->|Parameter|Type|Description|
|---|---|---|---|
|const|**scope**|[TUserDefined&#8203;Function&#8203;Scope](../TUserDefinedFunctionScope.md)|Defines if the custom function will be available globally to all ExcelFile instances or only to the ExcelFile instance where it was added\. It is recommended to add functions globally, unless you have different xls files with functions that might have the same name but could be implemented different\.|
|const|**location**|[TUserDefined&#8203;Function&#8203;Location](../TUserDefinedFunctionLocation.md)|Defines if the function will be inserted as a reference to a macro in the local sheet or in an external book or addin\.<br />This parameter is used only when adding formulas with user defined functions to a sheet\. It is not needed or used when recalculating those functions or when reading the text of a formula\.|
|const|**userFunction**|[TUserDefinedFunction](../TUserDefinedFunction/index.md)|Formula function we want to add\.|


## See also

* [TExcelFile](../TExcelFile/index.md)


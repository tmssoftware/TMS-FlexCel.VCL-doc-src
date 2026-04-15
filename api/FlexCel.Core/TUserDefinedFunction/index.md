---
uid: TUserDefinedFunction
description: TUserDefinedFunction
---

# TUserDefinedFunction Class

Inherit from this class to create your own user defined functions\. Make sure you read ['Using Excel's user defined functions (UDF)' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf) to get more information on what user defined functions are and how they are created\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUserDefinedFunction = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create\(string\)](Create.md#tuserdefinedfunctioncreatestring)<br />  [Create\(string, string\)](Create.md#tuserdefinedfunctioncreatestring-string)<br />|


## Methods

|Name|Description|
|---|---|
|[Evaluate](Evaluate.md)|Override this method to provide your own implementation on the function\.<br /><br />If this method throws an exception, it will not be handled and the recalculation will be aborted\. So if you want to return an error, return a [TFlxFormulaError&#8203;Value](../TFlxFormulaErrorValue.md) value\.<br /><br />**Do not use any global variable in this method**, it must be stateless and always return the same value when called with the same arguments\.<br /><br /><br />See ['Using excels user defined functions udf' in the Api Developer Guide](xref:ApiDeveloperGuide#using-excels-user-defined-functions-udf)[...[more]](Evaluate.md)|
|[CheckParameters](CheckParameters.md)|Checks that the parameter array has the expected number of arguments, and that no one is an Error\. If any argument is an error it is returned in ResultError, since the default in Excel is to stop processing arguments in a function when one is an error\.<br />|
|[GetSingleParameter](GetSingleParameter.md)|Returns a single value from a parameter\.<br />If the parameter is a cell range and the cell range has only one cell, this method will return the value of the cell, else it will return an error\.<br />|
|[TryGetDouble](TryGetDouble.md)|Tries to retrieve a double from a parameter, and return it if it can be converted or an error if not\.<br />|
|[TryGetDate](TryGetDate.md)|Tries to retrieve a date/time from a parameter, and return it if it can be converted or an error if not\.<br />|
|[TryGetDoubleList](TryGetDoubleList.md)|Tries to retrieve a list of double arguments from the parameters, starting at parameter startParam\.<br />Use this method for functions that accept a range of numeric values as an entry\. \(for example =Sum\(a1:a10\)\)|
|[TryGetString](TryGetString.md)|Tries to retrieve a string from a parameter, and return it if it can be converted or an error if not\.<br />|
|[TryGetBoolean](TryGetBoolean.md)|Tries to retrieve a boolean from a parameter, and return it if it can be converted or an error if not\.<br />|
|[TryGetCellRange](TryGetCellRange.md)|Tries to retrieve a cell range from a parameter, and return it if it can be converted or an error if not\.<br />|
|[TryGetArray](TryGetArray.md)|Tries to retrieve an array from a parameter, and return it if it can be converted or an error if not\.<br />|


## Properties

|Name|Description|
|---|---|
|[Name](Name.md)|Name that will be assigned to the function\.<br />|
|[InternalName](InternalName.md)|Name that will be used when saving xls \(biff8\) files\. Some functions are saved by Excel 2010 as \.xlfn\_Name when saving xls \(not xlsx\)\. This is the name that should be saved in the xls file, not the real name of the function\.<br />|



---
uid: TFormulaValue
description: TFormulaValue
---

# TFormulaValue Record

Represents a value inside a formula\. it might be an array of values in case it is an array formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TFormulaValue = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Empty](Empty.md)|Creates a formula value without value\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Double\)](Create.md#tformulavaluecreatedouble)<br />  [Create\(Int64\)](Create.md#tformulavaluecreateint64)<br />  [Create\(TDateTime\)](Create.md#tformulavaluecreatetdatetime)<br />  [Create\(string\)](Create.md#tformulavaluecreatestring)<br />  [Create\(Boolean\)](Create.md#tformulavaluecreateboolean)<br />  [Create\(TFlxFormulaErrorValue\)](Create.md#tformulavaluecreatetflxformulaerrorvalue)<br />  [Create\(TFormulaValueArray2\)](Create.md#tformulavaluecreatetformulavaluearray2)<br />  [Create\(TAddress\)](Create.md#tformulavaluecreatetaddress)<br />  [Create\(TSingleFormulaValue\)](Create.md#tformulavaluecreatetsingleformulavalue)<br />  [Create\(TAverageValue\)](Create.md#tformulavaluecreatetaveragevalue)<br />  [Create\(TArray\<TAddress>, Boolean\)](Create.md#tformulavaluecreatetarraytaddress-boolean)<br />  [Create\(Integer, Integer\)](Create.md#tformulavaluecreateinteger-integer)<br />  [Create\(TAddress, TAddress, Boolean\)](Create.md#tformulavaluecreatetaddress-taddress-boolean)<br />|
|[MissingArg](MissingArg.md)|Creates a formula value containing a missing argument\.<br />|
|[FromLambda](FromLambda.md)|Creates a formula value containing a Lambda\. Note that Lambdas are used internally only\.<br />You shouldn't use this overload, and a public TFormulaValue should never contain a lambda\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the formula is empty\.<br />|
|[HasValue](HasValue.md)|Returns true if the formula has a value\. This method is the same as not [IsEmpty](IsEmpty.md)|
|[IsNumber](IsNumber.md)|Returns true if the formula has a number\.<br />|
|[IsDateTime](IsDateTime.md)|Returns true if the formula has a datetime\. Note that formulas by default never have datetimes, they have numbers instead\.<br />|
|[IsString](IsString.md)|Returns true if the formula contains a string\.<br />|
|[IsBoolean](IsBoolean.md)|Returns true if the formula contains a boolean\.<br />|
|[IsError](IsError.md)|Returns true if the formula contains an error\.<br />|
|[IsArray](IsArray.md)|Returns true if the formula contains an array of values instead of a single value\.<br />|
|[IsMissingArg](IsMissingArg.md)|Returns true if the value is a missing argument from a function, like in the formula =MyFunction\(1, ,3\) where the second parameter is missing\.<br />|
|[IsCellAddress](IsCellAddress.md)|Returns true if the formula has a TCellAddress|
|[IsCellRange](IsCellRange.md)|Returns true if the formula contains a range of cells\.<br />|
|[IsRange3D](IsRange3D.md)|Returns true if the formula contains a range of cells spanning more than one sheet\.<br />|
|[IsAverage](IsAverage.md)|Returns true if the formula contains an Average value\. This value is used internally to calculate averages, formula results won't contain averages\.<br />|
|[IsLambda](IsLambda.md)|Returns true if the formula contains lambda function\.<br />|
|[AsNumber](AsNumber.md)|Returns the value of the formula if it contains a number\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsNumber](IsNumber.md) to see if the formula contains a number\.<br /><br /><br />|
|[AsDateTime](AsDateTime.md)|Returns the value of the formula if it contains a detetime\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsDateTime](IsDateTime.md) to see if the formula contains a datetime\.<br /><br /><br />|
|[AsString](AsString.md)|Returns the value of the formula if it contains a string\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsString](IsString.md) to see if the formula contains a string\.<br /><br /><br />|
|[AsBoolean](AsBoolean.md)|Returns the value of the formula if it contains a boolean\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsBoolean](IsBoolean.md) to see if the formula contains a boolean\.<br /><br /><br />|
|[AsError](AsError.md)|Returns the value of the formula if it contains an error\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsError](IsError.md) to see if the formula contains an error\.<br /><br /><br />|
|[AsCellAddress](AsCellAddress.md)|Returns the value of the formula if it contains a cell adress\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsCellAddress](IsCellAddress.md) to see if the formula contains a cell address\.<br /><br /><br />|
|[AsCellRange](AsCellRange.md)|Returns the value of the formula if it contains a range of cells\.<br />If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.<br /><br /><br />|
|[AsRange3D](AsRange3D.md)|Returns the value of the formula if it contains a range of cells covering many sheets\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsRange3D](IsRange3D.md) to see if the formula contains a range of cells in multiple sheets\.<br /><br /><br />|
|[AsAverage](AsAverage.md)|Returns the value of the formula if it contains an average\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsAverage](IsAverage.md) to see if the formula contains an average\.<br /><br /><br />|
|[AsLambda](AsLambda.md)|Returns the value of the formula if it contains a a lambda\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsLambda](IsLambda.md) to see if the formula contains a lambda\.<br /><br /><br />|
|[AsVariant](AsVariant.md)|Returns the formula result as a variant\.<br />|
|[AsTValue](AsTValue.md)|Returns the formula result as a TValue\.<br />|
|[ToString](ToString.md)|Converts the formula result to a string\.<br />|
|[ToStringInvariant](ToStringInvariant.md)|Converts the formula result to a string with invariant format\. This means that for example the number 1\.2 will be converted to the string '1\.2' even if in the active locale it would '1,2' because the decimal separator is a comma\. To get the number as a string in the current locale, use [ToString](ToString.md)|
|[AsArray](AsArray.md)|Returns the formula result as an array of values if the formula contains an array\. If the formula result is not an array, this method will throw an exception\.<br />|
|[TryAsArray](TryAsArray.md)|Will return the formula result if the formula result is an array, or nil if the formula result is something else\.<br />|
|[TryAsCellAddress](TryAsCellAddress.md)|Will return the formula result if the formula result is a cell address, or nil if the formula result is something else\.<br />|
|[TryToDouble](TryToDouble.md)|Tries to convert this value to a number, and returns true is possible\.<br />|
|[GetLength](GetLength.md)|Returns the length of any of the 2 possible dimensions of the array of TSingleFormulaValue|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from Double to TFormulaValue](op_Implicit.md#implicit-conversion-from-double-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to Double](op_Implicit.md#implicit-conversion-from-tformulavalue-to-double)<br />  [Implicit conversion from Extended to TFormulaValue](op_Implicit.md#implicit-conversion-from-extended-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to Extended](op_Implicit.md#implicit-conversion-from-tformulavalue-to-extended)<br />  [Implicit conversion from Integer to TFormulaValue](op_Implicit.md#implicit-conversion-from-integer-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to Integer](op_Implicit.md#implicit-conversion-from-tformulavalue-to-integer)<br />  [Implicit conversion from Int64 to TFormulaValue](op_Implicit.md#implicit-conversion-from-int64-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to Int64](op_Implicit.md#implicit-conversion-from-tformulavalue-to-int64)<br />  [Implicit conversion from TDateTime to TFormulaValue](op_Implicit.md#implicit-conversion-from-tdatetime-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to TDateTime](op_Implicit.md#implicit-conversion-from-tformulavalue-to-tdatetime)<br />  [Implicit conversion from string to TFormulaValue](op_Implicit.md#implicit-conversion-from-string-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to string](op_Implicit.md#implicit-conversion-from-tformulavalue-to-string)<br />  [Implicit conversion from Boolean to TFormulaValue](op_Implicit.md#implicit-conversion-from-boolean-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to Boolean](op_Implicit.md#implicit-conversion-from-tformulavalue-to-boolean)<br />  [Implicit conversion from TFlxFormulaErrorValue to TFormulaValue](op_Implicit.md#implicit-conversion-from-tflxformulaerrorvalue-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to TFlxFormulaErrorValue](op_Implicit.md#implicit-conversion-from-tformulavalue-to-tflxformulaerrorvalue)<br />  [Implicit conversion from TFormulaValueArray2 to TFormulaValue](op_Implicit.md#implicit-conversion-from-tformulavaluearray2-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to TFormulaValueArray2](op_Implicit.md#implicit-conversion-from-tformulavalue-to-tformulavaluearray2)<br />  [Implicit conversion from TAddress to TFormulaValue](op_Implicit.md#implicit-conversion-from-taddress-to-tformulavalue)<br />  [Implicit conversion from TAverageValue to TFormulaValue](op_Implicit.md#implicit-conversion-from-taveragevalue-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to TAverageValue](op_Implicit.md#implicit-conversion-from-tformulavalue-to-taveragevalue)<br />  [Implicit conversion from TSingleFormulaValue to TFormulaValue](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-tformulavalue)<br />  [Implicit conversion from TFormulaValue to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-tformulavalue-to-tsingleformulavalue)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ValueType](ValueType.md)|Returns the type of value stored in the formula\. \(a string, a number etc\)\. You can check for this directly or call the helper methods like [IsNumber](IsNumber.md) or [IsBoolean](IsBoolean.md)\. Those methods internally check for ValueType\.<br />|



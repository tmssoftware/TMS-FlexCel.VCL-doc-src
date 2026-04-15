---
uid: TSingleFormulaValue
description: TSingleFormulaValue
---

# TSingleFormulaValue Record

Represents a single value inside a formula\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TSingleFormulaValue = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Empty](Empty.md)|Creates a formula value without value\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Double\)](Create.md#tsingleformulavaluecreatedouble)<br />  [Create\(Int64\)](Create.md#tsingleformulavaluecreateint64)<br />  [Create\(TDateTime\)](Create.md#tsingleformulavaluecreatetdatetime)<br />  [Create\(string\)](Create.md#tsingleformulavaluecreatestring)<br />  [Create\(Boolean\)](Create.md#tsingleformulavaluecreateboolean)<br />  [Create\(TFlxFormulaErrorValue\)](Create.md#tsingleformulavaluecreatetflxformulaerrorvalue)<br />  [Create\(TAddress\)](Create.md#tsingleformulavaluecreatetaddress)<br />  [Create\(TXls3DRange\)](Create.md#tsingleformulavaluecreatetxls3drange)<br />  [Create\(TAverageValue\)](Create.md#tsingleformulavaluecreatetaveragevalue)<br />  [Create\(TArray\<TAddress>, Boolean\)](Create.md#tsingleformulavaluecreatetarraytaddress-boolean)<br />  [Create\(TAddress, TAddress, Boolean\)](Create.md#tsingleformulavaluecreatetaddress-taddress-boolean)<br />|
|[MissingArg](MissingArg.md)|Creates a formula value containing a missing argument\.<br />|
|[FromLambda](FromLambda.md)|Creates a formula value containing a Lambda\. Note that Lambdas are used internally only\.<br />You shouldn't use this overload, and a public TFormulaValue should never contain a lambda\.<br />|
|[ClearValue](ClearValue.md)|Makes the instance empty\.<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the formula is empty\.<br />|
|[HasValue](HasValue.md)|Returns true if the formula has a value\. This method is the same as not [IsEmpty](IsEmpty.md)|
|[IsNumber](IsNumber.md)|Returns true if the formula has a number\.<br />|
|[IsDateTime](IsDateTime.md)|Returns true if the formula has a datetime\. Note that formulas by default never have datetimes, they have numbers instead\.<br />|
|[IsString](IsString.md)|Returns true if the formula contains a string\.<br />|
|[IsBoolean](IsBoolean.md)|Returns true if the formula contains a boolean\.<br />|
|[IsError](IsError.md)|Returns true if the formula contains an error\.<br />|
|[IsMissingArg](IsMissingArg.md)|Returns true if the value is a missing argument from a function, like in the formula =MyFunction\(1, ,3\) where the second parameter is missing\.<br />|
|[IsCellAddress](IsCellAddress.md)|Returns true if the formula has a TCellAddress|
|[IsCellRange](IsCellRange.md)|Returns true if the formula contains a range of cells\.<br />|
|[IsRange3D](IsRange3D.md)|Returns true if the formula contains a range of cells spanning more than one sheet\.<br />|
|[IsAverage](IsAverage.md)|Returns true if the formula contains an Average value\. This value is used internally to calculate averages, formula results won't contain averages\.<br />|
|[IsLambda](IsLambda.md)|Returns true if the formula contains lambda function\. This is used internally to calculate, formula results won't contain lambdas\.<br />|
|[AsNumber](AsNumber.md)|Returns the value of the formula if it contains a number\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsNumber](IsNumber.md) to see if the formula contains a number\.<br /><br /><br />|
|[AsDateTime](AsDateTime.md)|Returns the value of the formula if it contains a detetime\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsDateTime](IsDateTime.md) to see if the formula contains a datetime\.<br /><br /><br />|
|[AsString](AsString.md)|Returns the value of the formula if it contains a string\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsString](IsString.md) to see if the formula contains a string\.<br /><br /><br />|
|[AsBoolean](AsBoolean.md)|Returns the value of the formula if it contains a boolean\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsBoolean](IsBoolean.md) to see if the formula contains a boolean\.<br /><br /><br />|
|[AsError](AsError.md)|Returns the value of the formula if it contains an error\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsError](IsError.md) to see if the formula contains an error\.<br /><br /><br />|
|[AsCellAddress](AsCellAddress.md)|Returns the value of the formula if it contains a cell adress\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsCellAddress](IsCellAddress.md) to see if the formula contains a cell address\.<br /><br /><br />|
|[AsCellRange](AsCellRange.md)|Returns the value of the formula if it contains a range of cells\.<br />If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.<br /><br /><br />|
|[AsRange3D](AsRange3D.md)|Returns the value of the formula if it contains a range of cells covering many sheets\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsRange3D](IsRange3D.md) to see if the formula contains a range of cells in multiple sheets\.<br /><br /><br />|
|[AsCellAddressString](AsCellAddressString.md)|Returns the value of the formula if it contains a range of cells\.<br />If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Different from [AsCellAddress](AsCellAddress.md), this method will return a string like "A1" instead of an array of [TAddress](../TAddress/index.md) object\.<br /><br /><br /><br />Check [IsCellAddress](IsCellAddress.md) to see if the formula contains a range of cells\.<br /><br /><br />|
|[AsCellRangeString](AsCellRangeString.md)|Returns the value of the formula if it contains a range of cells\.<br />If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Different from [AsCellRange](AsCellRange.md), this method will return a string like "A1:A10" instead of an array of [TAddress](../TAddress/index.md) object\.<br /><br /><br /><br />Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.<br /><br /><br />|
|[AsRange3DString](AsRange3DString.md)|Returns the value of the formula if it contains a range of cells\.<br />If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Different from [AsRange3D](AsRange3D.md), this method will return a string like "Sheet1:&#8203;Sheet2\!&#8203;A1:&#8203;A10" instead of a [TXls3DRange](../TXls3DRange/index.md) object\.<br /><br /><br /><br />Check [IsCellRange](IsCellRange.md) to see if the formula contains a range of cells\.<br /><br /><br />|
|[AsAverage](AsAverage.md)|Returns the value of the formula if it contains an average\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsAverage](IsAverage.md) to see if the formula contains an average\.<br /><br /><br />|
|[AsLambda](AsLambda.md)|Returns the value of the formula if it contains a lambda function\. If it contains other datatype, this method will throw an exception\.<br /><br /><br /><br />Check [IsLambda](IsLambda.md) to see if the formula contains a lambda function\.<br /><br /><br />|
|[AsVariant](AsVariant.md)|Returns the formula result as a variant\.<br />|
|[AsTValue](AsTValue.md)|Returns the formula result as a TValue\.<br />|
|[ToString](ToString.md)|Converts the formula result to a string\.<br />|
|[ToStringInvariant](ToStringInvariant.md)|Converts the formula result to a string with invariant format\. This means that for example the number 1\.2 will be converted to the string '1\.2' even if in the active locale it would '1,2' because the decimal separator is a comma\. To get the number as a string in the current locale, use [ToString](ToString.md)|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from Double to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-double-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to Double](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-double)<br />  [Implicit conversion from Extended to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-extended-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to Extended](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-extended)<br />  [Implicit conversion from Integer to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-integer-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to Integer](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-integer)<br />  [Implicit conversion from Int64 to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-int64-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to Int64](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-int64)<br />  [Implicit conversion from TDateTime to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-tdatetime-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to TDateTime](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-tdatetime)<br />  [Implicit conversion from string to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-string-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to string](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-string)<br />  [Implicit conversion from Boolean to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-boolean-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to Boolean](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-boolean)<br />  [Implicit conversion from TFlxFormulaErrorValue to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-tflxformulaerrorvalue-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to TFlxFormulaErrorValue](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-tflxformulaerrorvalue)<br />  [Implicit conversion from TAddress to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-taddress-to-tsingleformulavalue)<br />  [Implicit conversion from TAverageValue to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-taveragevalue-to-tsingleformulavalue)<br />  [Implicit conversion from TSingleFormulaValue to TAverageValue](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-taveragevalue)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ValueType](ValueType.md)|Returns the type of value stored in the formula\. \(a string, a number etc\)\. You can check for this directly or call the helper methods like [IsNumber](IsNumber.md) or [IsBoolean](IsBoolean.md)\. Those methods internally check for ValueType\.<br />|



---
uid: TCellValue
description: TCellValue
---

# TCellValue Record

Represents a value inside a cell\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TCellValue = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Empty](Empty.md)|Creates a cell value without value\.<br />|
|[Create](Create.md)|**Overloaded<br />**  [Create\(Double\)](Create.md#tcellvaluecreatedouble)<br />  [Create\(Int64\)](Create.md#tcellvaluecreateint64)<br />  [Create\(TDateTime\)](Create.md#tcellvaluecreatetdatetime)<br />  [Create\(string\)](Create.md#tcellvaluecreatestring)<br />  [Create\(TRichString\)](Create.md#tcellvaluecreatetrichstring)<br />  [Create\(Boolean\)](Create.md#tcellvaluecreateboolean)<br />  [Create\(TFlxFormulaErrorValue\)](Create.md#tcellvaluecreatetflxformulaerrorvalue)<br />  [Create\(TFormula\)](Create.md#tcellvaluecreatetformula)<br />  [Create\(Variant\)](Create.md#tcellvaluecreatevariant)<br />  [Create\(TValue\)](Create.md#tcellvaluecreatetvalue)<br />|
|[IsEmpty](IsEmpty.md)|Returns true if the cell is empty\.<br />|
|[HasValue](HasValue.md)|Returns true if the cell has a value\. This is the opposite of [IsEmpty](IsEmpty.md)|
|[IsNumber](IsNumber.md)|Returns true if the cell contains a number\. Note that cells with dates will be reported as Number too\.<br />|
|[IsDateTime](IsDateTime.md)|Returns true if the value is a DateTime\.<br />**Note:**:This value will never be true when reading cells from a file\.<br />When reading a file, dates are stored as number so they will be returned as numbers\.<br />This property only will return true if you manually created a TCellValue from a TDateTime\.<br /><br />To know if a cell has a date, you need to look at its format, not its value\.<br />|
|[IsString](IsString.md)|Returns true if the cell has a string\.<br />|
|[IsBoolean](IsBoolean.md)|Returns true if the cell has a boolean\.<br />|
|[IsError](IsError.md)|Returns true if the cell has an error like \#N/A\! or \#DIV0\!\.<br />Note that this only applies to error values entered directly in the cell\.<br />If the cell has a formula that returns \#N/A\!, then the cell has a formula and the formula has an error\. But the cell itself doesn't have an error\.<br />|
|[IsFormula](IsFormula.md)|Returns true if the cell has a formula\.<br />|
|[AsNumber](AsNumber.md)|Returns the value of the cell if it contains a number or a date\.<br />If the cell doesn't contain a number this method will raise an exception so you might want to check first the cell data type before calling it\.<br />|
|[AsDateTime](AsDateTime.md)|If the cell contains a datetime, it returns the value\. If not, it raises an Exception\. Remember that cells returned from a file will never have a datetime, they will have numbers instead\.<br />|
|[AsString](AsString.md)|If the cell contains a string, it returns the string\. If not, it raises an Exception\. To get a string with whatever value is in the class, use [ToString](ToString.md)|
|[ToString](ToString.md)|Returns a rich string with whatever the cell value is\. If this is an integer or a boolean, it will be converted to a string\.<br />|
|[ToSimpleString](ToSimpleString.md)|Returns a string without formatting\. This is equivalent to ToString\.ToString, but it can be faster\.<br />|
|[ToStringInvariant](ToStringInvariant.md)|Returns a string with whatever the cell value is\. If this is number, it will be converted to a string, using invariant format settings \(decimal separator will always be "\." for example\)\.<br />|
|[ToDateTime](ToDateTime.md)|Returns the value as a DateTime, if it can be converted, or DateTime\(0\) if it can't\.<br />|
|[ToNumberInvariant](ToNumberInvariant.md)|Returns the value as a number, if it can be converted, or 0 if it can't\. Note that this conversion uses invariant culture so even if your decimal separator is ",", the strings converted should be like "2\.0"|
|[AsBoolean](AsBoolean.md)|If the cell contains a boolean, it returns the value\. If not, it raises an exception\.<br />|
|[AsError](AsError.md)|If the cell contains an error, it returns the value\. If not, it raises an exception\.<br />|
|[AsFormula](AsFormula.md)|If the cell contains a formula, it returns the value\. If not, it raises an exception\.<br />|
|[AsVariant](AsVariant.md)|Returns the cell value as a variant\.<br />|
|[AsTValue](AsTValue.md)|Returns the cell value as a TValue\.<br />|
|[ClearValue](ClearValue.md)|Sets the value of the cell to empty\.<br />|


## Operators

|Name|Description|
|---|---|
|[Implicit Conversion](op_Implicit.md)|**Overloaded<br />**  [Implicit conversion from Double to TCellValue](op_Implicit.md#implicit-conversion-from-double-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Double](op_Implicit.md#implicit-conversion-from-tcellvalue-to-double)<br />  [Implicit conversion from Extended to TCellValue](op_Implicit.md#implicit-conversion-from-extended-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Extended](op_Implicit.md#implicit-conversion-from-tcellvalue-to-extended)<br />  [Implicit conversion from Integer to TCellValue](op_Implicit.md#implicit-conversion-from-integer-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Integer](op_Implicit.md#implicit-conversion-from-tcellvalue-to-integer)<br />  [Implicit conversion from Int64 to TCellValue](op_Implicit.md#implicit-conversion-from-int64-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Int64](op_Implicit.md#implicit-conversion-from-tcellvalue-to-int64)<br />  [Implicit conversion from TDateTime to TCellValue](op_Implicit.md#implicit-conversion-from-tdatetime-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TDateTime](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tdatetime)<br />  [Implicit conversion from string to TCellValue](op_Implicit.md#implicit-conversion-from-string-to-tcellvalue)<br />  [Implicit conversion from TCellValue to string](op_Implicit.md#implicit-conversion-from-tcellvalue-to-string)<br />  [Implicit conversion from TRichString to TCellValue](op_Implicit.md#implicit-conversion-from-trichstring-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TRichString](op_Implicit.md#implicit-conversion-from-tcellvalue-to-trichstring)<br />  [Implicit conversion from Boolean to TCellValue](op_Implicit.md#implicit-conversion-from-boolean-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Boolean](op_Implicit.md#implicit-conversion-from-tcellvalue-to-boolean)<br />  [Implicit conversion from TFlxFormulaErrorValue to TCellValue](op_Implicit.md#implicit-conversion-from-tflxformulaerrorvalue-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TFlxFormulaErrorValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tflxformulaerrorvalue)<br />  [Implicit conversion from TFormula to TCellValue](op_Implicit.md#implicit-conversion-from-tformula-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TFormula](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tformula)<br />  [Implicit conversion from TSingleFormulaValue to TCellValue](op_Implicit.md#implicit-conversion-from-tsingleformulavalue-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TSingleFormulaValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tsingleformulavalue)<br />  [Implicit conversion from TFormulaValue to TCellValue](op_Implicit.md#implicit-conversion-from-tformulavalue-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TFormulaValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tformulavalue)<br />  [Implicit conversion from Variant to TCellValue](op_Implicit.md#implicit-conversion-from-variant-to-tcellvalue)<br />  [Implicit conversion from TCellValue to Variant](op_Implicit.md#implicit-conversion-from-tcellvalue-to-variant)<br />  [Implicit conversion from TValue to TCellValue](op_Implicit.md#implicit-conversion-from-tvalue-to-tcellvalue)<br />  [Implicit conversion from TCellValue to TValue](op_Implicit.md#implicit-conversion-from-tcellvalue-to-tvalue)<br />|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ValueType](ValueType.md)|Data type of the cell\. All the properties like [IsNumber](IsNumber.md) check this ValueType to know what the cell contains\.<br />|



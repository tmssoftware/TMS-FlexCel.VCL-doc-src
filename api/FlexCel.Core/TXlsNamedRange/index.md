---
uid: TXlsNamedRange
description: TXlsNamedRange
---

# TXlsNamedRange Record

An Excel named range\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TXlsNamedRange = record;</code></pre>

## Fields

|Name|Description|
|---|---|
|[Name](Name.md)|The name of the range\.<br />|
|[SheetIndex](SheetIndex.md)|The Sheet index where the row and col properties apply\. 1\-based\. When RangeFormula is set, it is not used\.<br />|
|[NameSheetIndex](NameSheetIndex.md)|The sheet index for the name \(1 based\)\. A named range can have the same name than other as long as they are on different sheets\. The default value\(0\) means a global named range, not tied to any specific sheet\.<br />|
|[OptionFlags](OptionFlags.md)|Options of the range\. You can access the options by using the corresponding properties\. \(Hidden, BuiltIn, etc\)\.<br /><br />You can use this property to set them all at the same time\.<br /><br />You can get the properties by OR'ing the following values:<br /><br />01\. Name is hidden\. Corresponds to the property [Hidden](Hidden.md)\.<br /><br />02\. Name is a function\. Corresponds to the property [FunctionDef](FunctionDef.md)\.<br /><br />04\. Name is a VB procedure\. If set you also need to set 08 \(name is a macro\)\. Corresponds to the property[...[more]](OptionFlags.md)|
|[Top](Top.md)|Top of the range\.<br />|
|[Left](Left.md)|Left of the range\.<br />|
|[Bottom](Bottom.md)|Bottom of the range\.<br />|
|[Right](Right.md)|Right of the range\.<br />|
|[RangeFormula](RangeFormula.md)|This is a formula defining the range\. It can be used to define complex ranges\.<br />For example you can use "=&#8203;Sheet1\!&#8203;$A:&#8203;$B,&#8203;Sheet1\!&#8203;$1:&#8203;$2"&#8203;\.&#8203;<br />When this parameter is set, SheetIndex, Left, Top, Right and Bottom properties have no meaning\.<br /><br />Note that with **relative** references, we always consider "A1" to be the cell where the name is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br />|
|[Comment](Comment.md)|Returns the comment associated with the name, if there is one\. Comments are only available in Excel 2007, but they are saved too in xls file format\.<br />|


## Methods

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#txlsnamedrangecreate)<br />  [Create\(string, Integer, Integer, string\)](Create.md#txlsnamedrangecreatestring-integer-integer-string)<br />  [Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, string\)](Create.md#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-string)<br />  [Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer\)](Create.md#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer)<br />  [Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string\)](Create.md#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer-string)<br />  [Create\(string, Integer, Integer, Integer, Integer, Integer, Integer, Integer, string, string\)](Create.md#txlsnamedrangecreatestring-integer-integer-integer-integer-integer-integer-integer-string-string)<br />|
|[Equals](Equals.md)|Returns true if both objects are equal\.<br />|
|[GetHashCode](GetHashCode.md)|Returns the hashcode of the object\.<br />|
|[GetInternalName](GetInternalName.md)|Returns the string that corresponds to an internal name\.<br />|
|[ToString](ToString.md)|A human\-readable representation of the range\.<br />|
|[IsValidRangeName](IsValidRangeName.md)|Returns true if the string is a valid name for a named range\. Valid names must start with a letter or an underscore|
|[GetRanges](GetRanges.md)|**Overloaded<br />**  [GetRanges\(TCoreExcelFile\)](GetRanges.md#txlsnamedrangegetrangestcoreexcelfile)<br />  [GetRanges\(TCoreExcelFile, Integer\)](GetRanges.md#txlsnamedrangegetrangestcoreexcelfile-integer)<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|
|[Null](Null.md)|Creates an invalid Cell range with all coordinates being negative\.<br />|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|
|[Explicit Conversion](op_Explicit.md)|Converts from TXlsNamedRange instances to TXlsCellRange instances when you do an explicit cast\.|


## Properties

|Name|Description|
|---|---|
|[Hidden](Hidden.md)|True if the range is hidden\.<br />|
|[FunctionDef](FunctionDef.md)|True if the range is a function\.<br />|
|[VisualBasicProc](VisualBasicProc.md)|True if the range is a Visual Basic Procedure|
|[Proc](Proc.md)|True if the range is a function on a macro sheet\.<br />|
|[CalcExp](CalcExp.md)|True if the range contains a complex function\.<br />|
|[BuiltIn](BuiltIn.md)|True if the range is a built in name\. Built in names are 1 char long\.<br />|
|[FunctionGroup](FunctionGroup.md)|Specifies the function group index if the defined name refers to a function\. The function group defines the general category for the function\. This attribute is used when there is an add\-in or other code project associated with the file\.<br />|
|[PublishToServer](PublishToServer.md)|Indicates whether the defined name is included in the version of the workbook that is published to or rendered on a Web or application server\. This is new to Excel 2007\.<br />|
|[WorkbookParameter](WorkbookParameter.md)|indicates that the name is used as a workbook parameter on a version of the workbook that is published to or rendered on a Web or application server\. This is new to Excel 2007\.<br />|
|[CellRef](CellRef.md)|Gets or sets the string that defines the 2D\-range in A1 notation\.<br />|



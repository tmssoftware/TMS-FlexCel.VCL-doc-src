---
uid: TDataValidationInfo
description: TDataValidationInfo
---

# TDataValidationInfo Record

Contains the information to define a data validation in a range of cells\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TDataValidationInfo = record;</code></pre>

## Methods

|Name|Description|
|---|---|
|[Empty](Empty.md)|Empty constructor\. Creates a new instance of TDataValidationInfo without assigning any value\.<br />|
|[Create](Create.md)|Creates a new Data Validation condition with all parameters\.<br />|
|[CompareTo](CompareTo.md)|Compares the object with other\.<br />|
|[Equals](Equals.md)|Returns true if both objects are equal\.<br />|
|[IsNull](IsNull.md)|Returns true if the record doesn't have a defined value\.<br />|
|[HasValue](HasValue.md)|Returns true if the record has a defined value\. This is the inverse of [IsNull](IsNull.md)|


## Operators

|Name|Description|
|---|---|
|[Equality](op_Equality.md)|Adapts the = operator so it returns true when both instances have the same values\.|
|[Inequality](op_Inequality.md)|Adapts the \<> operator so it returns true when both instances have different values\.|


## Properties

|Name|Description|
|---|---|
|[ValidationType](ValidationType.md)|Type of validation we will be doing\.<br />|
|[Condition](Condition.md)|Condition used to apply the data validation\.<br />|
|[FirstFormula](FirstFormula.md)|Formula for the first condition of the data validation\. The text of the formula is limited to 255 characters\.<br />If [ExplicitList](ExplicitList.md) is true, this formula can contain a list of values\.<br /><br />Note that with **relative** references, we always consider "A1" to be the cell where the data validation is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br />|
|[SecondFormula](SecondFormula.md)|Formula for the second condition of the data validation, if it has two conditions\. The text of the formula is limited to 255 characters\.<br /><br />Note that with **relative** references, we always consider "A1" to be the cell where the data validation is\. This means that the formula: "=$A$1 \+ A1" when evaluated in Cell B8, will read "=$A$1 \+ B8"\. To provide a negative offset, you need to wrap the formula\.<br />For example "=A1048575" will evaluate to B7 when evaluated in B8\.<br />|
|[IgnoreEmptyCells](IgnoreEmptyCells.md)|If true Empty cells will not trigger data validation errors\.<br />|
|[InCellDropDown](InCellDropDown.md)|When the [ValidationType](ValidationType.md) parameter is a list, this property indicates whether to display a drop down box or not\.<br />|
|[ExplicitList](ExplicitList.md)|If true, [FirstFormula](FirstFormula.md) contains a list of values\.<br />In this case, Formula1 **must** be a formula of the type: ="string", where string is a list of values separated by Character\(0\)\.<br />For example, in C\# Formula1 could be: *="&#8203;Apples\\0Lemmons\\0Melons*   In Delphi\.NET, Formula1 could be: *'="Apples' \+ \#0 \+ 'Lemmons' \+ \#0 \+ 'Melons'*|
|[ShowErrorBox](ShowErrorBox.md)|If true, an error box dialog will be shown when the user enters an invalid value\.<br />|
|[ErrorBoxCaption](ErrorBoxCaption.md)|Caption of the Error Alert box\. Note that this text cannot be longer than 32 characters\.<br />Extra characters will be truncated\. If this parameter is null, the default Error alert will be displayed\.<br />If [ShowErrorBox](ShowErrorBox.md) is false, this parameter does nothing\.<br />|
|[ErrorBoxText](ErrorBoxText.md)|Text on the Error Alert box\. Note that this text cannot be longer than 225 characters\.<br />Extra characters will be truncated\. If this parameter is null, the default Error alert will be displayed\.<br />If [ShowErrorBox](ShowErrorBox.md) is false, this parameter does nothing\.<br />|
|[ShowInputBox](ShowInputBox.md)|If true, a box showing a message will be shown when the user selecte the cell\.<br />|
|[InputBoxCaption](InputBoxCaption.md)|Caption of the Input Message box\. Note that this text cannot be longer than 32 characters\.<br />Extra characters will be truncated\. If this parameter is null, the Input box will display the default message\.<br />if [ShowInputBox](ShowInputBox.md) is false, this parameter does nothing\.<br />|
|[InputBoxText](InputBoxText.md)|Text on the Input Message box\. Note that this text cannot be longer than 255 characters\.<br />Extra characters will be truncated\. If this parameter is null, the Input box will display the default message\.<br />if [ShowInputBox](ShowInputBox.md) is false, this parameter does nothing\.<br />|
|[ErrorIcon](ErrorIcon.md)|Icon to display in the error box\.<br />|
|[ImeMode](ImeMode.md)|The IME \(input method editor\) mode enforced by this data validation\.<br />|



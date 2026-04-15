---
uid: TTokenType
description: TTokenType
---

# TTokenType Enumeration

Enumerates the different kind of tokens you can find in a formula

## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|CellAddress|0|A single cell address in the same sheet or to other sheet\. See also CellRange for other tokens that can contain addresses\.<br />|
|RelativeCellAddress|1|A cell address relative to the cell where the formula is\. This token is used mostly in names\.<br />|
|CellRange|2|A range of cells\. See CellAddress for single cell references\.<br />|
|RelativeCellRange|3|A cell range relative to the cell where the formula is\. This token is used mostly in names\.<br />|
|FunctionToken|4|A function like "Sum" or "If"|
|OperatorToken|5|An operator like "\+" or "\-"|
|RangeOp|6|Operator in ranges, like "Union" or "Intersection"|
|Whitespace|7|Whitespace like " "|
|Parenthesis|8|A parenthesis surrounding the last token\. Note that this token is not used in the formula \(since RPN doesn't need parenthesis\) but it is there so Excel can display them\.<br />|
|Name|9|A named range|
|Data|10|Constant data, like "Hello" and 1 in the formula: "=IF\(A1 = 1,,"Hello"\)"|
|DataArray|11|An array of constant data\.<br />|
|MissingArgument|12|A missing argument for a function\. For example the second parameter in the formula: "=IF\(A1 = 1,,"Hello"\)"|
|ReferenceError|13|A token representing a reference to a cell or range that doesn't exist\.<br />|
|StructuredReference|14|A reference to a Table\.<br />|
|LambdaCallName|15|When you call a name like "=MyName\(5\)" and MyName has a lambda function\.<br />|
|LambdaParameterReference|16|A reference to a parameter inside a LET or LAMBDA function\.<br />|
|LambdaParameterDefinition|17|A definition of a parameter inside a LET or LAMBDA function\.<br />|
|Unsupported|18|This token is not supported by FlexCel\.<br />|



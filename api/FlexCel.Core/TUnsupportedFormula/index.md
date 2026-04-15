---
uid: TUnsupportedFormula
description: TUnsupportedFormula
---

# TUnsupportedFormula Class

An unsupported formula, the cell it is in, and the reason why it is not supported\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">TUnsupportedFormula = class(TFlexCelObject);</code></pre>

## Constructors

|Name|Description|
|---|---|
|[Create](Create.md)|**Overloaded<br />**  [Create](Create.md#tunsupportedformulacreate)<br />  [Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string\)](Create.md#tunsupportedformulacreatetunsupportedformulaerrortype-tcelladdress-string-string)<br />  [Create\(TUnsupportedFormulaErrorType, TCellAddress, string, string, TCellAddressWithFileNameArray\)](Create.md#tunsupportedformulacreatetunsupportedformulaerrortype-tcelladdress-string-string-tcelladdresswithfilenamearray)<br />|


## Methods

|Name|Description|
|---|---|
|[GetHashCode](GetHashCode.md)|Hashcode for this object\.<br />|
|[Equals](Equals.md)|Returns true if both objects have the same values\.<br />|


## Properties

|Name|Description|
|---|---|
|[ErrorType](ErrorType.md)|Type of error\.<br />|
|[Cell](Cell.md)|Cell where the formula is \(1 based\)|
|[FunctionName](FunctionName.md)|If the error is [TUnsupported&#8203;Formula&#8203;Error&#8203;Type.&#8203;Missing&#8203;Function](../TUnsupportedFormulaErrorType.md) then this is the name of the missing function\.<br />If the error is [TUnsupported&#8203;Formula&#8203;Error&#8203;Type.&#8203;External&#8203;Reference](../TUnsupportedFormulaErrorType.md) then this is the name of the file not found\.<br />|
|[FileName](FileName.md)|This property has the name of the physical file being evaluated, and can be of use when evaluating linked files\. If the files are opened from a stream or not from a physical place, it will be null\.<br />|
|[StackTrace](StackTrace.md)|This property only has a value is the error is [TUnsupported&#8203;Formula&#8203;Error&#8203;Type.&#8203;Circular&#8203;Reference](../TUnsupportedFormulaErrorType.md)\. It contains a list of all the cells that lead to this cell having to recalculate itself\. Note that this stack is limited to the last [TExcelFile.&#8203;Cell&#8203;Stack&#8203;Trace&#8203;MaxSize](../TExcelFile/CellStackTraceMaxSize.md) elements to avoid consuming too much memory\.<br />|


